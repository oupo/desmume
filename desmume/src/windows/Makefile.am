include $(top_srcdir)/src/desmume.mk

bin_PROGRAMS = desmume

desmume_CPPFLAGS = -D_WIN32_IE=0x0600 -DWINVER=0x0501
desmume_CFLAGS = -mwindows -msse2

desmume_CPPFLAGS += $(LIBAGG_CFLAGS) $(GLIB_CFLAGS) $(GTHREAD_CFLAGS)

desmume_LDADD = ../libdesmume.a  $(LIBAGG_LIBS) $(GLIB_LIBS) $(GTHREAD_LIBS) \
	-lwinmm -lvfw32 -lshlwapi -lole32 \
	-lddraw -ldinput8 -ldsound -ldxerr8 -ldxguid \
	-l7z -loleaut32 -L/usr/lib/w32api -luuid

if HAVE_GDB_STUB
desmume_LDADD += ../gdbstub/libgdbstub.a
endif

if HAVE_LUA
desmume_LDADD += $(LUA_LIBS)
desmume_CPPFLAGS += $(LUA_CFLAGS)
endif

resources.o: resources.res
	windres resources.res $@

desmume_LDADD += resources.o
desmume_DEPENDENCIES = resources.o


desmume_SOURCES = \
	../driver.h \
	../driver.cpp \
	../metaspu/SndOut.cpp \
	../metaspu/SndOut.h \
	../metaspu/Timestretcher.cpp \
	../metaspu/win32/ConfigSoundtouch.cpp \
	../metaspu/win32/Dialogs.h \
	../metaspu/SoundTouch/3dnow_win.cpp \
	../metaspu/SoundTouch/AAFilter.cpp \
	../metaspu/SoundTouch/AAFilter.h \
	../metaspu/SoundTouch/BPMDetect.h \
	../metaspu/SoundTouch/cpu_detect.h \
	../metaspu/SoundTouch/cpu_detect_x86_gcc.cpp \
	../metaspu/SoundTouch/FIFOSampleBuffer.cpp \
	../metaspu/SoundTouch/FIFOSampleBuffer.h \
	../metaspu/SoundTouch/FIFOSamplePipe.h \
	../metaspu/SoundTouch/FIRFilter.cpp \
	../metaspu/SoundTouch/FIRFilter.h \
	../metaspu/SoundTouch/mmx_optimized.cpp \
	../metaspu/SoundTouch/RateTransposer.cpp \
	../metaspu/SoundTouch/RateTransposer.h \
	../metaspu/SoundTouch/SoundTouch.cpp \
	../metaspu/SoundTouch/SoundTouch.h \
	../metaspu/SoundTouch/sse_optimized.cpp \
	../metaspu/SoundTouch/STTypes.h \
	../metaspu/SoundTouch/TDStretch.cpp \
	../metaspu/SoundTouch/TDStretch.h \
	../metaspu/SoundTouch/WavFile.cpp \
	../metaspu/SoundTouch/WavFile.h \
	../wxdlg/wxdlg3dViewer.cpp \
	../wxdlg/wxdlg3dViewer.h \
	7zip.cpp \
	7zip.h \
	7zipstreams.h \
	AboutBox.cpp \
	AboutBox.h \
	aviout.cpp \
	aviout.h \
	cheatsWin.cpp \
	cheatsWin.h \
	colorctrl.cpp \
	colorctrl.h \
	console.cpp \
	console.h \
	CWindow.cpp \
	CWindow.h \
	FirmConfig.cpp \
	FirmConfig.h \
	gbaslot_config.cpp \
	gbaslot_config.h \
	hotkey.cpp \
	hotkey.h \
	inputdx.cpp \
	inputdx.h \
	luaconsole.cpp \
	main.cpp \
	main.h \
	mic.cpp \
	ogl.cpp \
	OpenArchive.cpp \
	OpenArchive.h \
	pathsettings.cpp \
	pathsettings.h \
	recentroms.cpp \
	recentroms.h \
	replay.cpp \
	replay.h \
	resource.h \
	snddx.cpp \
	snddx.h \
	throttle.cpp \
	throttle.h \
	winpcap.h \
	winutil.cpp \
	winutil.h \
	filter/2xsai.cpp \
	filter/bilinear.cpp \
	filter/epx.cpp \
	filter/filter.h \
	filter/hq2x.cpp \
	filter/lq2x.cpp \
	filter/scanline.cpp \
	userconfig/userconfig.h \
	disView.cpp \
	disView.h \
	ginfo.cpp \
	ginfo.h \
	IORegView.cpp \
	IORegView.h \
	lightView.cpp \
	lightView.h \
	mapView.cpp \
	mapView.h \
	matrixView.cpp \
	matrixView.h \
	memView.cpp \
	memView.h \
	oamView.cpp \
	oamView.h \
	palView.cpp \
	palView.h \
	ram_search.cpp \
	ram_search.h \
	ramwatch.cpp \
	ramwatch.h \
	soundView.cpp \
	soundView.h \
	tileView.cpp \
	tileView.h
