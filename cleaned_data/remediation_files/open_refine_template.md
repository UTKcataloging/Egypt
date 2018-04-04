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
<identifier type="pid">{{cells["PID"].value}}</identifier>
<identifier type="legacy">{{cells["legacy_identifier"].value}}</identifier>
<identifier type="acquisition">{{cells["acquisition_no"].value}}</identifier>
{{if(isBlank(cells['acquisition_no_2'].value), '', '<identifier type="acquisition">' + cells['acquisition_no_2'].value + '</identifier>')}}
{{if(isBlank(cells["title"].value),'', '<titleInfo><title>' + cells['title'].value + '</title></titleInfo>')}}
{{if(isBlank(cells["supplied_title"].value),'', '<titleInfo supplied="yes"><title>' + cells['supplied_title'].value + '</title></titleInfo>')}}
<abstract>{{cells['abstract'].value}}</abstract>
{{'<originInfo>' + if(isBlank(cells['date'].value), '', '<dateCreated>' + cells['date'].value + '</dateCreated>') + if(isBlank(cells['date_edtf'].value), '', '<dateCreated encoding="edtf">' + cells['date_edtf'].value + '</dateCreated>') +
if(isBlank(cells['publisher'].value), '', '<publisher>' + cells['publisher'].value + '</publisher>') + '</originInfo>'}}
{{'<physicalDescription>' + '<extent>' + cells['extent'].value + '</extent><form authority="aat" valueURI="' + cells['form_URI'].value + '">' + cells['form'].value + '</form>' + if(isBlank(cells['form_2'].value), '', '<form authority="aat" valueURI="' + if(isBlank(cells['form_URI_2'].value), '', cells['form_URI_2'].value) + '">' + cells['form_2'].value + '</form>') + '<internetMediaType>image/jpeg</internetMediaType><digitalOrigin>reformatted digital</digitalOrigin></physicalDescription>'}}
<relatedItem displayLabel="Project" type="host"><titleInfo><title>Nineteenth and Early Twentieth Century Images of Egypt</title></titleInfo></relatedItem>
{{if(isBlank(cells['creator'].value), '', '<name' + if(isBlank(cells['name_type'].value), '', ' type="' + cells['name_type'].value + '"') + if(isBlank(cells['creator_URI'].value), '>', ' valueURI="' + cells['creator_URI'].value + '">') + if(isBlank(cells['creator'].value), '', '<namePart>' + cells['creator'].value + '</namePart>') + if(isBlank(cells['active_dates'].value), '', '<namePart type="date">' + cells['active_dates'].value + '</namePart>') + if(isBlank(cells['dob_dod'].value), '', '<namePart type="date">' + cells['dob_dod'].value + '</namePart>') + if(isBlank(cells['nationality'].value), '', '<description>' + cells['nationality'].value + '</description>') + if(isBlank(cells['role'].value), '', '<role><roleTerm type="text" authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/pht">Photographer</roleTerm></role>') + '</name>')}}
{{if(isBlank(cells['subject_geographic'].value), '', '<subject><geographic' + if(isBlank(cells['sub_geo_auth'].value), '', ' authority="' + cells['sub_geo_auth'].value + '"') + if(isBlank(cells['sub_geo_URI'].value), '>', ' valueURI="' + cells['sub_geo_URI'].value + '">') + cells['subject_geographic'].value + '</geographic></subject>')}}
{{if(isBlank(cells['subject_geographic_2'].value), '', '<subject><geographic' + if(isBlank(cells['sub_geo_auth_2'].value), '', ' authority="' + cells['sub_geo_auth_2'].value + '"') + if(isBlank(cells['sub_geo_URI_2'].value), '>', ' valueURI="' + cells['sub_geo_URI_2'].value + '">') + cells['subject_geographic_2'].value + '</geographic></subject>')}}
{{if(isBlank(cells['subject_name'].value), '', '<subject><name' + if(isBlank(cells['sub_nam_URI'].value), '>', ' authority="naf" valueURI="' + cells['sub_nam_URI'].value + '">') + '<namePart>' + cells['subject_name'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name_2'].value), '', '<subject><name' + if(isBlank(cells['sub_nam_URI2'].value), '>', ' authority="naf" valueURI="' + cells['sub_nam_URI2'].value + '">') + '<namePart>' + cells['subject_name_2'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name_3'].value), '', '<subject><name' + if(isBlank(cells['sub_nam_URI3'].value), '>', ' authority="naf" valueURI="' + cells['sub_nam_URI3'].value + '">') + '<namePart>' + cells['subject_name_3'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name_4'].value), '', '<subject><name' + if(isBlank(cells['sub_nam_URI4'].value), '>', ' authority="naf" valueURI="' + cells['sub_nam_URI4'].value + '">') + '<namePart>' + cells['subject_name_4'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_topic'].value), '', '<subject><topic' + if(isBlank(cells['sub_top_URI'].value), '>', ' authority="lcsh" valueURI="' + cells['sub_top_URI'].value + '">') + cells['subject_topic'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_2'].value), '', '<subject><topic' + if(isBlank(cells['sub_top_URI_2'].value), '>', ' authority="lcsh" valueURI="' + cells['sub_top_URI_2'].value + '">') + cells['subject_topic_2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_3'].value), '', '<subject><topic' + if(isBlank(cells['sub_top_URI_3'].value), '>', ' authority="lcsh" valueURI="' + cells['sub_top_URI_3'].value + '">') + cells['subject_topic_3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_4'].value), '', '<subject><topic' + if(isBlank(cells['sub_top_URI_4'].value), '>', ' authority="lcsh" valueURI="' + cells['sub_top_URI_4'].value + '">') + cells['subject_topic_4'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_5'].value), '', '<subject><topic' + if(isBlank(cells['sub_top_URI_5'].value), '>', ' authority="lcsh" valueURI="' + cells['sub_top_URI_5'].value + '">') + cells['subject_topic_5'].value + '</topic></subject>')}}
{{if(isBlank(cells['language'].value), '', '<language><languageTerm type="code" authority="iso639-2b">' + cells['language'].value + '</languageTerm></language>')}}
{{if(isBlank(cells['language_2'].value), '', '<language><languageTerm type="code" authority="iso639-2b">' + cells['language_2'].value + '</languageTerm></language>')}}
<typeOfResource>still image</typeOfResource>
<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2017033007">Frank H. McClung Museum of Natural History and Culture</physicalLocation></location>
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/no2017033007">Frank H. McClung Museum of Natural History and Culture</recordContentSource><languageOfCataloging><languageTerm type="code" authority="iso639-2b">eng</languageTerm></languageOfCataloging></recordInfo>
<note displayLabel="Intermediate Provider">University of Tennessee, Knoxville. Libraries</note>
{{if(isBlank(cells['credit_line'].value), '', '<note>' + cells['credit_line'].value + '</note>')}}
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
<note displayLabel="Local Rights">{{cells['rights_McClung'].value}}</note>
</mods>
```

## Row Separator

**LEAVE BLANK**

## Suffix

```
</modsCollection>
```