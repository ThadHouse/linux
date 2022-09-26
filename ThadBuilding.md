make ni-pkg -j60 LOCALVERSION=""

scp ni-install/arm/boot/ni_zynq_custom_runmodekernel.itb admin@roborio-9999-frc.local:/boot/linux_runmode.itb
scp ni-install/arm/headers/module-versioning-image.squashfs admin@roborio-9999-frc.local:/usr/local/natinst/tools/module-versioning-image.squashfs
cd ni-install/arm/lib/modules/
tar cz . | ssh admin@roborio-9999-frc.local tar xz -C /lib/modules
