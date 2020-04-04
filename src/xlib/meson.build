files = [
  'audio.c',
  'dbus.c',
  'drawing.c',
  'event.c',
  'filesys.c',
  'freetype.c',
  'globals.c',
  'gtk.c',
  'main.c',
  'mmenu.c',
  'screen_grab.c',
  'tray.c',
  'v4l.c',
  'video.c',
  'window.c',
  '../posix/filesys.c'
]

deps = [
  dependency('freetype2'),
  dependency('glib-2.0'),
  dependency('gtk+-3.0'),
  dependency('libv4l2'),
  dependency('x11'),
  dependency('xrender'),
]

libutoxNATIVE = static_library('utoxNATIVE', files, dependencies: deps)
