# ld4ptemplates
A starter set of Resource Templates for Sinopia, based on the state of Library of Congress BFE Profiles (https://github.com/lcnetdev/verso/tree/master/data/profiles) as of August 7, 2019.

Changes made to the LC Profiles and Resource Templates to make them compatible with Sinopia:
1. changed property type `lookupResource` to `lookup`
2. changed one example of property type `list` to `lookup` (in Prints & Photographs profile)
3. LC templates declared a stricter schema than the one the Sinopia Profile Editor outputs, so when attempting to upload into the Editor, there were some Profiles that had a problem with having a default literal but not a default URI. Opened these in the Profile Editor and exported, which reset the schema to 0.0.9 and then they loaded in to the Editor with no problems.
4. revised address of external lookup sources from http... to https.... or added QA urn where needed
5. removed duplicate propertyURIs in templates (various strategies used, see notes in [Loading LC Profiles spreadsheet](https://docs.google.com/spreadsheets/d/1j2OUoXBmmvfC-vCnG02ynoQGFB5Q-pFsnRSszleZ78w/) (NOTE: did not fix all of these problems, but fixed several so we can see how these templates look in Sinopia and decide if we like the fix; see details in spreadsheet)
6. "Subject" fields that use the "subject composer": LC uses property type = `list`, Sinopia doesn't support, changed some of these to be a lookup to authorized headings (did not change all, but enough of them to see how it looks; see details in spreadsheet)
7. changed all Profile and Resource Template ID prefixes from `lc` to `ld4p`
8. changed dates on all Profiles and Resource Templates to `2019-08-19`
9. changed authors on all Profiles and Resource Templates from `NDMSO` to `LD4P`
10. added prefix to Profile titles `LD4P`
11. added suffix to Profile Descriptions: `based on LC profile as of Aug-07-2019`
12. added `_` prefix to all the titles for "starting point" Resource Templates so they sort first in the list of templates in Sinopia. (NOTE: on LC BFE, there's a starting point called Notated Music, RDA Expression. Unsure what Resource Template that uses so it's not reflected as a starting point in Sinopia.)
13. renamed generically named Resource Templates, for example, "BIBFRAME Item" renamed to "\_Cartographic Item (BIBFRAME)"
14. for Resource Templates in Profiles that include a starting point Resource Template, added remark `based on LC template [LC template ID]`

The [Loading LC Profiles spreadsheet](https://docs.google.com/spreadsheets/d/1j2OUoXBmmvfC-vCnG02ynoQGFB5Q-pFsnRSszleZ78w/) documents the changes made. The **Changes to Profiles** tab shows changes made to the Profile files to get them to import into Sinopia, and the **Changes by Resource Template** tab shows changes made to get the Resource Templates to open successfully once loaded.

NOTE:
As of August 19, 2019, these templates are on the [Sinopia development site](http://development.sinopia.io) for review, with the exception of Resource Templates from following Profiles (BIBFRAME 2.0 Sound Recording-Analog.json, BIBFRAME 2.0 Sound Recording-Audio Cassette.json, BIBFRAME 2.0 Sound Recording-Audio CD-R.json, BIBFRAME 2.0 Sound Recording-Audio CD.json, Prints & Photographs.json) (see the [Loading LC Profiles spreadsheet](https://docs.google.com/spreadsheets/d/1j2OUoXBmmvfC-vCnG02ynoQGFB5Q-pFsnRSszleZ78w/) spreadsheet, **Changes by Resource Template** tab for what remains to be done with Resource Templates from those Profiles)

NOTE:
Profiles in the LC Repo that were not added to this ld4ptemplates repo:
   - BIBFRAME 2.0 Monograph (Non-Latin).json (formerly known as BIBFRAME 2.0 Monograph (Non-Roman)). Per LC, this is the same as the Monograph template with the exception of the `literal-lang` property type. Since Sinopia literals can always have language specified, we don't use this property type, and the regular Monograph profile accommodates the non-Latin language needs.
   - BIBFRAME 2.0 Topic.json. Uses property type `list` (which we don't use in Sinopia).
