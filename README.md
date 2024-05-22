# bugs
# KVM.VFIO.os:Fedora.guest:Windows11
sch: https://www.google.com/search?q=swtpm+at+%2Fusr%2Fbin%2Fswtpm+does+not+support+TPM+2

## bug report:
- https://bugzilla.redhat.com/show_bug.cgi?id=2278905
- https://bugzilla.redhat.com/show_bug.cgi?id=2272971

## discuss:
- https://discussion.fedoraproject.org/t/unable-to-create-new-virt-manager-vm-with-software-tpm-on-fedora-40/114254
  - from: https://discussion.fedoraproject.org/t/tpm-does-not-work-virt-manager-fedora-40/114455

- https://discussion.fedoraproject.org/t/creating-new-vm-with-tpm-using-virt-manager-results-in-selinux-related-error/114917
- https://discussion.fedoraproject.org/t/talk-cannot-launch-libvirt-virtual-machines-after-upgrade-to-fedora-40/114009

## Solution:
works: false
`fixfiles -R libvirt-daemon-driver-qemu,libvirt-daemon-log restore && systemctl restart virtqemud virtlogd`
- [Comment 24](https://bugzilla.redhat.com/show_bug.cgi?id=2272971#c24)

### Disable SELinux
works: true
https://docs.fedoraproject.org/en-US/quick-docs/selinux-changing-states-and-modes/
