# Changelog for Affaldshåndtering DK Home Assistant Integration

  **Date**: `2024-03-10`

  This is a Hotfix release, only adding missing containers for some municipalities.

  I am sorry for these frequent releases, but this will most likely go on for a little while, until we mapped all the containers to the right Category. If you are missing a container, please add this to your configuration file:
```yaml
logger:
  default: warning
  logs:
    custom_components.affalddk: error
    pyrenoweb: error
```
And create an issue with the data from the logfile, and the Municipality that has the issue.

  ## What's Changed

- Fixing the Genbrug category for Hvidovre kommune
- Fixing the Genbrug category for Greve kommune
- Fixing the Genbrug category for Egedal kommune
- Bump dependency `pyrenoweb` to 2.0.10

---------------------------

<details>
  <summary><b>PREVIOUS CHANGES</b></summary>

  ## Version 2.0.2

  **Date**: `2024-03-09`

  ## What's Changed

  This is a Hotfix release, only adding missing containers for some municipalities

- Add missing containers for Rudersdal and Høje Taastrup. Closing [#15](https://github.com/briis/affalddk/issues/15) and [#16](https://github.com/briis/affalddk/issues/16)
- Optimied a few SVG files.
- Bump dependency `pyrenoweb` to 2.0.9


  ## Version 2.0.1

  **Date**: `2024-03-07`

  ## What's Changed

- Fixing wrong Issue Link address. Closing [#10](https://github.com/briis/affalddk/issues/10)
- Bump pyrenoweb to 2.0.5 Closing wrong types of garbage types in Egedal and Allerød [#6](https://github.com/briis/affalddk/issues/6)
- Handling the case where the same Road exists more than once in a Municipality. There is now a requirement to enter the Zipcode of the Address when setting up a new entity in Home Assistant. Closing Issue [#5](https://github.com/briis/affalddk/issues/5)
- Fixing missing containers in Aalborg. Closing [#11](https://github.com/briis/affalddk/issues/11)
- Added Rudersdal back to the list as they do work with this Integration. Closing [#8](https://github.com/briis/affalddk/issues/8)
- Bump dependency `pyrenoweb` to 2.0.6


  ## Version 2.0.0

  **Date**: `2024-03-04`

  ## What's Changed
  * Even though it says V2.0.0, this is the first release of this Integration. Please see the [README.md](https://github.com/briis/affalddk/blob/main/README.md) for a descriptin and installation instructions.
</details>

---------------------------
<details>
  <summary><b>VERSION 2.0.0-Beta-3</b></summary>

  ## Version 2.0.0-Beta-3

  **Date**: `2024-03-04`

  ## What's Changed
  * Bump ruff from 0.2.2 to 0.3.0 by @dependabot in https://github.com/briis/affalddk/pull/1
  * Version 2 beta3 by @briis in https://github.com/briis/affalddk/pull/2

  ## New Contributors
  * @dependabot made their first contribution in https://github.com/briis/affalddk/pull/1
  * @briis made their first contribution in https://github.com/briis/affalddk/pull/2

  **Full Changelog**: https://github.com/briis/affalddk/compare/2.0.0-beta2...v2.0.0-beta3

</details>

---------------------------
<details>
  <summary><b>VERSION 2.0.0-Beta-2</b></summary>

  ## Version 2.0.0-Beta-2

  **Date**: `2024-03-03`

  ### Changes

  Please see the [README.md](https://github.com/briis/affalddk/blob/main/README.md) before installation.

  This integration replaces the [RenoWeb integration](https://github.com/briis/renoweb), which will no longer be maintained.

  This is a complete rewrite of the RenowWeb V1.x Integration as the API this uses is slowly being phased out, and we needed to find a new way of collecting the data.

  If you were a previous user of Renoweb, you would have had to de-install the Integration before upgrading, as Unique ID's of all sensors would have been new, thus having to change your Automations, Scripts and Dashboard entries.
  With that in mind I decided to also use the opportunity to change the domain name of the Integration to `affalddk` So why change the name and not just give it a new version number?

  For a long time I wanted to have this Integration part of the Default HACS store, but in order to do that, you need to have Logo and icon images in the Home Assistant Brand Database. As Renoweb does not really have a logo by itself, I could not create one, as this could violate their rights to the name. But calling it something that is not related directly to Renoweb, gives me the possibility to invent my own logo and thus getting this added to the Default HACS store.

  If you were a previous user of Renoweb the Major changes to this integration are:

  - I now use a new API. The V1 API was based on a Renoweb API that is being phased ot, and over the last few months I have seen more and more municipalities disappearing from the supported municipalities. The new API is the same most Municipalities use, when you go to their official web page and search for your address and then get Pickup Schedules.
  - The `Sensors` are new, and not named the same way as the V1 sensors. Thus there is no upgrade path. With each sensor I now also iclude the official Pictograms as Entity Pictures, which you can use in your dashboard. **Note**: This image files must be installed manually - please see the README file).
  - There is a new local `Calendar` entity created, which has a full-day event every time there is a Pick-up. The event will contain a Description and what content is being picked up.
  - The `Binary Sensors` have not been created. If anyone uses these, raise an issue on Github.

  I have now been through all Municipalities and checked if they work with this Integration. There are 47 Munipalities that will work , and if you don't see your municipality in the Dropdown List, then it will not work.

</details>

