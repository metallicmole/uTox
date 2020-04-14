files = [
  'utox_av.c',
  'audio.c',
  'video.c',
  'filter_audio.c',
  ]

deps = [
  dependency('openal'),
  dependency('vpx'),
  dependency('toxcore'),
  dependency('opus'),
  ]

libutoxAV = static_library('utoxAV', files, dependencies: deps)
