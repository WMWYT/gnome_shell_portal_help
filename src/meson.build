
tools_cflags = '-DLOCALEDIR="@0@"'.format(localedir)
tools_deps = [gio_dep, gjs_dep]

if have_networkmanager
  executable('gnome-shell-portal-helper',
    'gnome-shell-portal-helper.c', portal_resources,
    c_args: tools_cflags,
    dependencies: tools_deps,
    include_directories: [conf_inc],
    install_dir: libexecdir,
    install: true
  )
endif