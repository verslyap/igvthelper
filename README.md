# igvthelper
igvthelper is a simple bash script that creates vgvt vGPUs for intel graphics hardware on compatible linux systems.

The configuration file is located at /etc/igvthelper/igvthelper.conf.  Each line of the configuration file containes the information necessary to create a vGPU.  The layout for the configuration file is roughly as follows:

#Lines with a poundsign are comments
#Each line starts with the word device, a friendly name, a uuid, and the vGPU type
device examplevgpu 32fb066b-dcab-4c65-9b1d-cf2d5c18d869 i915-GVTg_V5_8

igvthelper can also be run with the --types option.  This will list the available vGPU types that can be created.

igvthelper --types
i915-GVTg_V5_4
low_gm_size: 128MB high_gm_size: 512MB fence: 4 resolution: 1920x1200 weight: 4
i915-GVTg_V5_8
low_gm_size: 64MB high_gm_size: 384MB fence: 4 resolution: 1024x768 weight: 2

Or the --list options which simply outputs /etc/igvthelper/igvthelper.conf for convenience.

It also includes a systemd until file that can be enabled to create the vGPUs automatically at boot time.
