Old Bailey Online Prisoner Defences 1751-1900
==============

This dataset is released under a Creative Commons Attribution-ShareAlike 4.0 International Licence

[![License: CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/80x15.png)](http://creativecommons.org/licenses/by-sa/4.0/)


Introduction
-------------

This dataset has been created from [Old Bailey Online (OBO)](http://www.oldbaileyonline.org) XML data. It consists of all prisoner defence statements that could be identified in trials in the Old Bailey Proceedings between 1751 and 1900. The dataset has been created primarily in order to explore the [Voices of Authority](https://www.digitalpanopticon.org/?page_id=221) research theme of the [Digital Panopticon](http://www.digitalpanopticon.org) project. It's made available here for other researchers who may find it of interest.

The data covers a period in which the English criminal trial (for felonies) profoundly changed: in the mid-18th century few lawyers were involved and the trial was conceived as a direct encounter between victim as prosecutor, and the defendant who was expected to conduct their own defence. By 1900, lawyers were in charge, and trial procedures were increasingly bureaucratic.

For more information on trial procedures and the Old Bailey, please refer to the background information at http://www.oldbaileyonline.org.

Data creation
--------------

In addition to using OBO data as its direct source material, the dataset would not have been possible without the [Old Bailey Corpus (OBC)](http://fedora.clarin-d.uni-saarland.de/oldbailey/). OBC has added linguistic tagging to about a quarter of the Proceedings sessions, and this restructuring has made it possible to see speech data within the Proceedings in new ways. Thus, it became much clearer from OBC that prisoner defences (and, indeed, prisoners' statements more generally) are quite consistently labelled in the Proceedings text, and that defences tend to appear in certain places and forms that could be identified and extracted from the full OBO data for text mining and linguistic analysis.

Structured data from the OBO has then been added to the texts: all available defendant personal information (including gender and age), and offence, verdict and sentence categories, to make it possible to explore the effectiveness of particular kinds of defence narrative, or variations by gender or type of offence.

Data table
--------------

This is version 1.0 of the data (March 2017).

file: **obo_defences_v1.tsv**

Notes:

* normally there is one statement per defendant per trial, but there can be more than one
* statements such as "I leave my defence to my counsel" or "I am guilty" have been left in the data, even though they are not exactly defences
* sometimes prisoners put in written defences that were read out in court, or non-English speakers' defences were communicated through an interpreter; I have excluded these where they are indicated


| Field label | Description |
| ----------- | ------------ |
| uid | unique identifier in the dataset |
| trial | OBO trial ID |
| p_no | paragraph number in the trial |
| def_id | OBO defendant ID |
| sess_date | OBO session date, YYYYMMDD |
| trial_def_count | number of defendants in the trial |
| prefix | words immediately preceding the statement, usually "Prisoner's Defence" or similar. |
| txt | the statement |
| word_count | count of words in the statement |
| given | given name of defendant |
| surname | surname of defendant |
| gender | gender of defendant |
| age_years | age of defendant (NULL if not present) |
| occupation | occupation of defendant, as described in the trial report |
| offcat | OBO offence category |
| offsubcat | OBO offence subcategory |
| vercat | OBO verdict category |
| versubcat | OBO verdict subcategory |
| puncat | OBO sentence category |
| punsubcat | OBO sentence subcategory |


Offence, verdict and sentence categories and subcategories
--------------------------------------------------

### Offences

| offcat | offsubcat |
| ------- | ---------- |
| breakingPeace | assault |
| breakingPeace | barratry |
| breakingPeace | libel |
| breakingPeace | other |
| breakingPeace | riot |
| breakingPeace | threateningBehaviour |
| breakingPeace | vagabond |
| breakingPeace | wounding |
| damage | arson |
| damage | other |
| deception | bankrupcy |
| deception | forgery |
| deception | fraud |
| deception | other |
| deception | perjury |
| kill | infanticide |
| kill | manslaughter |
| kill | murder |
| kill | other |
| kill | pettyTreason |
| miscellaneous | concealingABirth |
| miscellaneous | conspiracy |
| miscellaneous | habitualCriminal |
| miscellaneous | illegalAbortion |
| miscellaneous | kidnapping |
| miscellaneous | other |
| miscellaneous | pervertingJustice |
| miscellaneous | piracy |
| miscellaneous | returnFromTransportation |
| royalOffences | coiningOffences |
| royalOffences | other |
| royalOffences | religiousOffences |
| royalOffences | seditiousLibel |
| royalOffences | seditiousWords |
| royalOffences | seducingAllegiance |
| royalOffences | taxOffences |
| royalOffences | treason |
| sexual | assaultWithIntent |
| sexual | assaultWithSodomiticalIntent |
| sexual | bigamy |
| sexual | indecentAssault |
| sexual | keepingABrothel |
| sexual | other |
| sexual | rape |
| sexual | sodomy |
| theft | animalTheft |
| theft | burglary |
| theft | embezzlement |
| theft | extortion |
| theft | gameLawOffence |
| theft | grandLarceny |
| theft | housebreaking |
| theft | mail |
| theft | other |
| theft | pettyLarceny |
| theft | pocketpicking |
| theft | receiving |
| theft | shoplifting |
| theft | simpleLarceny |
| theft | stealingFromMaster |
| theft | theftFromPlace |
| violentTheft | highwayRobbery |
| violentTheft | other |
| violentTheft | robbery |


### Verdicts

| vercat | versubcat |
| ------- | ----------- |
| guilty |   |
| guilty | chanceMedley |
| guilty | insane |
| guilty | lesserOffence |
| guilty | manslaughter |
| guilty | pleadedGuilty |
| guilty | pleadedPartGuilty |
| guilty | theftunder100s |
| guilty | theftunder1s |
| guilty | theftunder40s |
| guilty | theftunder5s |
| guilty | withRecommendation |
| miscVerdict |  |
| miscVerdict | noAgreement |
| miscVerdict | postponed |
| miscVerdict | unfitToPlead |
| notGuilty |  |
| notGuilty | accidentalDeath |
| notGuilty | directed |
| notGuilty | fault |
| notGuilty | noEvidence |
| notGuilty | nonComposMentis |
| notGuilty | noProsecutor |
| notGuilty | selfDefence |
| notGuilty notGuilty | noEvidence |
| specialVerdict |  |

### Sentences

| puncat | punsubcat |
| -------- | ------------ |
| corporal |  |
| corporal | pillory |
| corporal | privateWhipping |
| corporal | publicWhipping |
| corporal | whipping |
| death |  |
| death | burning |
| death | deathAndDissection |
| death | drawnAndQuartered |
| death | executed |
| death | hangingInChains |
| death | respited |
| death | respitedForPregnancy |
| imprison |  |
| imprison | hardLabour |
| imprison | houseOfCorrection |
| imprison | insanity |
| imprison | newgate |
| imprison | otherInstitution |
| imprison | penalServitude |
| imprison | preventiveDetention |
| miscPunish |  |
| miscPunish | branding |
| miscPunish | fine |
| miscPunish | forfeiture |
| miscPunish | militaryNavalDuty |
| miscPunish | sureties |
| noPunish |  |
| noPunish | pardon |
| noPunish | sentenceRespited |
| transport |   |