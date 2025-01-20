# Ignition || meson.build
# --------------------------------
# Meson build configuration.
#
# Authors: @MaxineToTheStars <https://github.com/MaxineToTheStars>
# ----------------------------------------------------------------

# Project Declaration
project(
    'ignition',
    'c',
    default_options: {'c_std': 'c99'},
    license: 'GPLv3',
    license_files: ['LICENSE'],
    meson_version: '>= 1.5.0',
    version: '0.1.0-dev',
)

# Run the globber script
# NOTE: This is not really recommended
# https://github.com/mesonbuild/meson/blob/master/docs/markdown/FAQ.md#but-i-really-want-to-use-wildcards
globber_source = run_command('bash', './scripts/globber.sh', '-s', capture: true, check: true)
parsed_source_files = globber_source.stdout().strip().replace('./', '').split('\n')

# Include the full include directory
include_directory = include_directories('include')

# Project Executable
executable(
    'ignition',
    parsed_source_files,
    include_directories: include_directory,
)
