# OpenRefine Template for Egypt (migration)

---

## Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```

## Row Template

```
<mods>
<identifier type="local">{{cells["adminDB"].value}}</identifier>
<identifier type="legacy">{{cells["legacy_identifier"].value}}</identifier>
<identifier type="acquisition">{{cells["acquisition_no"].value}}</identifier>
{{if(isBlank(cells["title"].value),'', '<titleInfo><title>' + cells['title'].value + '</title></titleInfo>')}}
{{if(isBlank(cells["supplied_title"].value),'', '<titleInfo supplied="yes"><title>' + cells['supplied_title'].value + '</title></titleInfo>')}}


{{'<originInfo>' + if(isBlank(cells['date'].value), '', '<dateIssued>' + cells['date'].value + '</dateIssued>') + if(isBlank(cells['date2'].value), '', '<dateIssued encoding="edtf">' + cells['date2'].value + '</dateIssued>') +
if(isBlank(cells['publisher'].value), '', '<publisher>' + cells['publisher'].value + '</publisher>') + '</originInfo>'}}
{{if(isBlank(cells['credit_line'].value), '', '<note>' + cells['credit_line'].value + '</note>')}}
<physicalDescription><extent>{{cells['extent'].value}}</extent><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form><internetMediaType>image/jpeg</internetMediaType></physicalDescription>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>Nineteenth and Early Twentieth Century Images of Egypt</title></titleInfo></relatedItem>

{{if(isBlank(cells['creator'].value), '', '<name><namePart>' + cells['creator'].value + '</namePart>' + if(isBlank(cells['creator'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/pht">Photographer</roleTerm></role>') + '</name>')}}

<subject><topic authority="lcsh" valueURI="{{cells['subject1_URI'].value}}">{{cells['subject1'].value}}</topic></subject>
<subject><topic authority="lcsh" valueURI="{{cells['subject2_URI'].value}}">{{cells['subject2'].value}}</topic></subject>
{{if(isBlank(cells['subject3'].value), '', '<subject><topic' + if(isBlank(cells['subject3_URI'].value), '>', ' authority="lcsh" valueURI="' + cells['subject3_URI'].value + '">') + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['language'].value), '', '<language><languageTerm type="text" authority="iso639-2b">' + cells['language'].value + '</languageTerm></language>')}}

<typeOfResource>still image</typeOfResource>
<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2017033007">Frank H. McClung Museum of Natural History and Culture</physicalLocation>
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/no2017033007">Frank H. McClung Museum of Natural History and Culture</recordContentSource></recordInfo>
<note displayLabel="Intermediate Provider">University of Tennessee, Knoxville. Libraries</note>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```