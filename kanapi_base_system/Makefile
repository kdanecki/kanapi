#
#  Copyright (c) 2012 Jacek Danecki <jacek.m.danecki@gmail.com>
#
# This file is part of KaNaPi project
#
# KaNaPi is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# KaNaPi is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with KaNaPi.  If not, see <http://www.gnu.org/licenses/>.

# this file is not updated to the latest version
# and was not tested yet
#

DIRS0="diffutils gzip bzip2 linux net-tools wget Python libffi glib pkg-config pixman kbproto strace xproto \
xextproto xtrans libxml2 libxslt xcb-proto libpthread-stubs libXau libxcb inputproto util-macros libX11 \
glproto makedepend libpciaccess libdrm dri2proto libXext damageproto fixesproto libXfixes libXdamage \
expat groff llvm MesaLib xf86driproto openssl xcmiscproto bigreqsproto randrproto renderproto fontsproto \
videoproto compositeproto recordproto scrnsaverproto resourceproto xineramaproto libxkbfile freetype libfontenc \
libXfont xf86dgaproto xorg-server perl xinit libICE libSM libXt libXmu libXpm libXaw xterm xf86-input-keyboard xf86-input-mouse \
xf86-video-vesa xf86-video-fbdev XML-Parser intltool xkbcomp xkeyboard-config mkfontdir bdftopcf mkfontscale \
font-cursor-misc font-util xorg-cf-files imake rplay vtwm atk fontconfig libpng cairo tiff libjpeg \
gdk-pixbuf libXrender pango gtk+ libxfce4util dbus-glib dbus ExtUtils-Depends ExtUtils-PkgConfig Glib \
xfconf libxfceui libwnck xfwm4 garcon URI exo xfce4-panel xfdesktop procps font-adobe-100dpi font-adobe-75dpi \
font-bitstream-type1 font-xfree86-type1 libXcursor gdb vim vala menu-cache libexif libfm pcmanfm hicolor-icon-theme \
ruby git SDL smpeg SDL_mixer SDL_ttf SDL_image sge rubysdl wireless_tools kmod libusb usbutils pci_ids gobject-introspection \
gperf udev libnl nss-with-nspr dhcp NetworkManager iso-codes wpa_supplicant"

DIRS1="diffutils"

DIRS=$(DIRS1)

prepare: check1 copy

copy:
	@cp Makefile kanapi_system/kanapi_build/out
	@for d in "$(DIRS)" ; do \
		cd scripts/$${d} ; ./prepare  ; cd ../.. ; \
	done

check1:
	@for d in "$(DIRS)" ; do \
		if ! test -f "scripts/$${d}/prepare"  ; then echo "$${d} missing" ; fi \
	done

compile: 
	@for d in "$(DIRS)" ; do \
		cd $${d}-* ; ./$${d}-*.compile ; cd .. ; \
	done


