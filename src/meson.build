compiler = meson.get_compiler('c')

dirminini = include_directories('../third-party/minini/dev')
libminini = shared_library('libminini',
                           '../third-party/minini/dev/minIni.c',
                           install : true)
libminini_dep = declare_dependency(include_directories : dirminini,
                                  link_with : libminini)

dirqrcodegen = include_directories('../third-party/qrcodegen/c')
libqrcodegen = shared_library('libqrcodegen',
                              '../third-party/qrcodegen/c/qrcodegen.c',
                              install : true)
libqrcodegen_dep = declare_dependency(include_directories: dirqrcodegen,
                                      link_with : libqrcodegen)

subdir('native')
subdir('layout')
subdir('ui')
subdir('av')

deps = [
  dependency('libsodium'),
  libminini_dep,
  libqrcodegen_dep,
]

args = ['-Wall',
        '-Wextra',
        '-Wpointer-arith',
        '-Wimplicit-fallthrough=5',
        '-Werror=implicit-function-declaration',
        '-Wformat=0',
        '-Wno-misleading-indentation',
        '-fno-strict-aliasing',
        '-fPIC']

src =  [
  'avatar.c',
  'chatlog.c',
  'chrono.c',
  'command_funcs.c',
  'commands.c',
  'devices.c',
  'file_transfers.c',
  'filesys.c',
  'flist.c',
  'friend.c',
  'globals.c',
  'groups.c',
  'inline_video.c',
  'logging.c',
  'main.c',
  'messages.c',
  'notify.c',
  'qr.c',
  'screen_grab.c',
  'self.c',
  'settings.c',
  'sized_string.h',
  'stb.c',
  'text.c',
  'theme.c',
  'tox.c',
  'tox_callbacks.c',
  'ui.c',
  'ui_i18n.c',
  'updater.c',
  'utox.c',
  'window.c',
]

executable('utox',
           src,
           dependencies: deps,
           c_args: args,
           link_with: [libutoxAV, libutoxNATIVE, libutoxUI]
          )
