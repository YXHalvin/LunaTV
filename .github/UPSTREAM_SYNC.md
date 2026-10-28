# Upstream synchronization

This repository is a fork of [SzeMeng76/LunaTV](https://github.com/SzeMeng76/LunaTV).

A scheduled job on the owner's VPS checks upstream `main` daily at 03:17 Asia/Shanghai time and merges new commits into this fork. The job uses a deploy key scoped to this repository. It never force-pushes. If your changes conflict with upstream, the job stops and leaves the fork unchanged until the conflict is resolved.

To inspect sync results on the VPS, run `tail -n 50 /var/log/lunatv-sync.log`. To run it manually, run `/usr/local/sbin/lunatv-sync-upstream`.

The GitHub Actions workflow in this fork is a fallback. GitHub Actions is currently disabled for the account, so the VPS job performs the scheduled sync.
