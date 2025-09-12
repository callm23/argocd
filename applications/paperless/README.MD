# Paperless

Container runs as uid=1000 and gid=1000

```bash
# change owner to UID=1000/GID=1000
chown -R 1000:1000 /volume2/proxmox/kubernetes/nfs/paperless/data
chown -R 1000:1000 /volume2/proxmox/kubernetes/nfs/paperless/media
chown -R 1000:1000 /volume2/proxmox/kubernetes/nfs/paperless/consume/

# Owner can read, write and execute
# Group members can read and execute
chmod -R 750 /volume2/proxmox/kubernetes/nfs/paperless/data
chmod -R 750 /volume2/proxmox/kubernetes/nfs/paperless/media/
chmod -R 750 /volume2/proxmox/kubernetes/nfs/paperless/consume/
```
