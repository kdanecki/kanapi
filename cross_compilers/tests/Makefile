include ../scripts/config.kanapi

test_binutils test_glibc test_gmp test_linux test_mpc test_mpfr: 
	@echo "!!! tests for $@ missing !!!"

test_gcc: test_gcc0.c test_gcc1.c
	@echo "tests for $@ for TARGET=$(KANAPI_TARGET_NAME)"
	@if [ ! -d $(KANAPI_BASE)/tests_results ] ; then mkdir $(KANAPI_BASE)/tests_results ; fi
	. ./set_variables; echo $$PATH;  $(KANAPI_BASE)/gcc-$(gcc_ver)/bin/$(KANAPI_TARGET_NAME)-gcc test_gcc0.c -Wall -o $(KANAPI_BASE)/tests_results/test_gcc0
	. ./set_variables; echo $$PATH;  $(KANAPI_BASE)/gcc-$(gcc_ver)/bin/$(KANAPI_TARGET_NAME)-gcc test_gcc1.c -Wall -o $(KANAPI_BASE)/tests_results/test_gcc1
	. ./set_variables; echo $$PATH;  $(KANAPI_BASE)/gcc-$(gcc_ver)/bin/$(KANAPI_TARGET_NAME)-gcc test_lm.c -Wall -o $(KANAPI_BASE)/tests_results/test_lm -lm

test_libstdcpp: test_libstdcpp.cpp test_threads.cpp
	@echo "tests for $@ for TARGET=$(KANAPI_TARGET_NAME)"
	@if [ ! -d $(KANAPI_BASE)/tests_results ] ; then mkdir $(KANAPI_BASE)/tests_results ; fi
	. ./set_variables; echo $$PATH;  $(KANAPI_BASE)/gcc-$(gcc_ver)/bin/$(KANAPI_TARGET_NAME)-g++ test_libstdcpp.cpp -Wall -lstdc++ -o $(KANAPI_BASE)/tests_results/test_libstdcpp
	. ./set_variables; echo $$PATH;  $(KANAPI_BASE)/gcc-$(gcc_ver)/bin/$(KANAPI_TARGET_NAME)-g++ test_threads.cpp -Wall -lstdc++ -std=c++11 -o $(KANAPI_BASE)/tests_results/test_threads -pthread

