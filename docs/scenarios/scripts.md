## Scripts

Provision scripts
Most scenarios utilise shared scripts to reduce the amount of programming and maintenance.  Every script that supports use in multiple scenarios is stored in /shared-content/scripts/modules.
As an example of this reuse the Provisioner.ps1 from the Qlik Sense - Single Node can be evaluated.  These scripts can be reused in any scenario.

### Note:
The Shared-content folder is sourced from the [qlik-automation-core](https://github.com/Qlik-Partner-Tools/qlik-automation-core) repository that was initialised during the configuration of the environment.

### Provisioner.ps1 script
```
& c:\shared-content\scripts\modules\q-user-setup.ps1

& c:\shared-content\scripts\modules\qs-getBinary.ps1

& c:\shared-content\scripts\modules\qs-initial-cfg.ps1

& c:\shared-content\scripts\modules\qs-install.ps1

& c:\shared-content\scripts\modules\qs-post-cfg.ps1

& c:\shared-content\scripts\modules\qs-update.ps1

& c:\shared-content\scripts\modules\q-provisioned.ps1
```