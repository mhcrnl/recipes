custom_target('recipes.db.h',
              input: ['recipes.db'],
              output: ['recipes.db.h'],
              command: [recipe_extract, '@INPUT@'],
              capture: true,
              build_by_default: true)

custom_target('chefs.db.h',
              input: ['chefs.db'],
              output: ['chefs.db.h'],
              command: [recipe_extract, '--chefs', '@INPUT@'],
              capture: true,
              build_by_default: true)

install_data(   'images/american.png',
                'images/big-american.png',
                'images/big-chinese.png',
                'images/big-french.jpg',
                'images/big-indian.jpg',
                'images/big-italian.png',
                'images/big-mediterranean.png',
                'images/big-nordic.jpg',
                'images/big-turkish.png',
                'images/chinese.png',
                'images/french.jpg',
                'images/indian.jpg',
                'images/italian.png',
                'images/mediterranean.png',
                'images/nordic.jpg',
                'images/turkish.png',
                install_dir: join_paths([pkgdatadir,'images']))

install_data('sounds/complete.oga',
             install_dir: join_paths([pkgdatadir,'sounds']))

install_data('chefs.db',
             'picks.db',
             'recipes.db',
             install_dir: pkgdatadir)

install_data('org.gnome.Recipes-mime.xml',
             install_dir: join_paths([datadir, 'mime/packages']))

msgfmt = find_program('msgfmt')

custom_target('desktop-file',
              output: 'org.gnome.Recipes.desktop',
              input: files('org.gnome.Recipes.desktop.in'),
              install: true,
              install_dir: join_paths([datadir,'applications']),
              command: [msgfmt, '--desktop', '-d', '../po', '--template', '@INPUT@', '-o', '@OUTPUT@'])

custom_target('appdata',
              output: 'org.gnome.Recipes.appdata.xml',
              input: files('appdata/org.gnome.Recipes.appdata.xml.in'),
              install: true,
              install_dir: join_paths([datadir,'appdata']),
              command: [msgfmt, '--xml', '-d', '../po', '--template', '@INPUT@', '-o', '@OUTPUT@'])

configure_file(input: 'org.gnome.Recipes.service.in',
               output: 'org.gnome.Recipes.service',
               configuration: conf,
               install_dir: join_paths([datadir,'dbus-1/services']))

gnome.compile_schemas()

install_data('org.gnome.Recipes.gschema.xml',
             install_dir: schemadir)

install_data(   'icons/16x16/org.gnome.Recipes.png',
                'icons/16x16/org.gnome.Recipes-symbolic.symbolic.png',
                install_dir: join_paths([datadir,'icons/hicolor/16x16/apps']))
install_data(   'icons/24x24/org.gnome.Recipes.png',
                'icons/24x24/org.gnome.Recipes-symbolic.symbolic.png',
                install_dir: join_paths([datadir,'icons/hicolor/24x24/apps']))
install_data(   'icons/32x32/org.gnome.Recipes.png',
                'icons/32x32/org.gnome.Recipes-symbolic.symbolic.png',
                install_dir: join_paths([datadir,'icons/hicolor/32x32/apps']))
install_data(   'icons/48x48/org.gnome.Recipes.png',
                'icons/48x48/org.gnome.Recipes-symbolic.symbolic.png',
                install_dir: join_paths([datadir,'icons/hicolor/48x48/apps']))
install_data(   'icons/512x512/org.gnome.Recipes.png',
                'icons/512x512/org.gnome.Recipes-symbolic.symbolic.png',
                install_dir: join_paths([datadir,'icons/hicolor/512x512/apps']))
install_data(   'icons/symbolic/org.gnome.Recipes-symbolic.svg',
                install_dir: join_paths([datadir,'icons/hicolor/symbolic/apps']))
