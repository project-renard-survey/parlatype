tests = [
	'player',
	'progressdialog',
	'wavedata',
	'waveloader',
	'waveviewer',
]

test_data = [
	'data/test1.ogg',
]

foreach t: tests
	exe = executable(
		t, '@0@.c'.format(t),
		install: false,
		dependencies: [ libparlatype_dep, gstreamer ],
	)

	test(
		t, exe,
		args: [ '--tap', '-k' ],
		env: [
			'G_TEST_SRCDIR=@0@'.format(meson.current_source_dir()),
			'G_TEST_BUILDDIR=@0@'.format(meson.current_build_dir()),
		],
	)
endforeach

