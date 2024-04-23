project('gnome-shell-portal-helper', 'c',
  version: '42.4',
  meson_version: '>= 0.58.0',
  license: 'GPL-3.0'
)

gio_req = '>= 2.56.0'
gjs_req = '>= 1.71.1'
gtk_req = '>= 3.15.0'
bt_req = '>= 3.9.0'
mutter_api_version = '10'
nm_req = '>= 1.10.4'
secret_req = '>= 0.18'
gst_req = '>= 0.11.92'


prefix = get_option('prefix')

datadir = join_paths(prefix, get_option('datadir'))
prefix = get_option('prefix')

gio_dep = dependency('gio-2.0', version: gio_req)
gjs_dep = dependency('gjs-1.0', version: gjs_req)
bt_dep = dependency('gnome-bluetooth-3.0', version: bt_req, required: false)

nm_deps = []
if get_option('networkmanager')
  nm_deps += dependency('libnm', version: nm_req)
  nm_deps += dependency('libsecret-1', version: secret_req)

  have_networkmanager = true
else
  have_networkmanager = false
endif

have_soup2 = get_option('soup2')
localedir = join_paths(datadir, 'locale')

x11_dep = dependency('x11')
gtk_dep = dependency('gtk+-3.0', version: gtk_req)

gst_dep = dependency('gstreamer-1.0', version: gst_req, required: false)
gst_base_dep = dependency('gstreamer-base-1.0', required: false)
pipewire_dep = dependency('libpipewire-0.3', required: false)

recorder_deps = []
enable_recorder = gst_dep.found() and gst_base_dep.found() and pipewire_dep.found()
if enable_recorder
  recorder_deps += [gst_dep, gst_base_dep, gtk_dep, x11_dep]
endif

datadir = join_paths(prefix, get_option('datadir'))
libexecdir = join_paths(prefix, get_option('libexecdir'))

gnome = import('gnome')

conf_inc = include_directories('.')

subdir('js')
subdir('src')