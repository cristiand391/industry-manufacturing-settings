### Create scratch org

`sfdx force:org:create -f config/project-scratch-def.json -s -a industry-man-set -v $DEVHUBUSERNAME --durationdays=1`

### Modify manufacturing settings in the org
Open org:
`sfdx force:org:open`

Go to Setup > Manufacturing > Enable Sales Agreement

### Retrieve settings

```bash
sfdx force:source:retrieve --manifest package.xml

=== Retrieved Source
FULL NAME                TYPE      PROJECT PATH
───────────────────────  ────────  ─────────────────────────────────────────────────────────────────────────
IndustriesManufacturing  Settings  force-app/main/default/settings/IndustriesManufacturing.settings-meta.xml
```

File `IndustriesManufacturing.settings-meta.xml` should be:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<IndustriesManufacturingSettings xmlns="http://soap.sforce.com/2006/04/metadata">
    <enableIndManufacturing>true</enableIndManufacturing>
    <enableIndustriesMfgAccountForecast>false</enableIndustriesMfgAccountForecast>
    <enableIndustriesMfgAdvForecast>false</enableIndustriesMfgAdvForecast>
    <enableIndustriesMfgIAS>false</enableIndustriesMfgIAS>
    <enableIndustriesMfgTargets>false</enableIndustriesMfgTargets>
</IndustriesManufacturingSettings>
```
