OBV: Old Bailey Voices 1780-1880
==============

This dataset is released under a Creative Commons Attribution-ShareAlike 4.0 International Licence

[![License: CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/80x15.png)](http://creativecommons.org/licenses/by-sa/4.0/)


Introduction
-------------

**OBV** is derived from two sources: the [Old Bailey Corpus (version 2) (OBC)](http://fedora.clarin-d.uni-saarland.de/oldbailey/) and the [Old Bailey Online (OBO)](http://www.oldbaileyonline.org). It contains data from all **single defendant trials** (21023 defendants) in 227 sessions of the Old Bailey Proceedings between 1780 and 1880 which have had linguistic markup added by the Old Bailey Corpus project. 

The dataset has been created in order to explore the [Voices of Authority](https://www.digitalpanopticon.org/?page_id=221) research theme of the [Digital Panopticon](http://www.digitalpanopticon.org) project. It's made available here for other researchers who may find it of interest.

For this project it was essential to correctly associate defendants with their spoken words (not a concern for OBC), as we intend to trace their histories and long-term outcomes using the Digital Panopticon's record linkage. The difficulties involved in ensuring this was done correctly in trials with multiple defendants (in fact, it's quite often impossible!), led to the decision to restrict this dataset to single-defendant trials.

The data has two components:  

* a new version of the tagged speech data from OBC with some additional tagging and OBO defendant IDs.
* summary data for each defendant (obv_defendants_trials.tsv) containing biographical and trial information 

This is version 2.0 of the data (OBV2), January 2017.


Summary data 
------------------

**obv_defendants_trials.tsv**

This contains data for *all* single defendants in OBC-tagged sessions, not just OBC-tagged trials. 

It includes information about whether there is OBC-tagged speech a) for the trial and b) for the defendant; word counts for the total text of a trial,  all OBC-tagged speech, and for the defendant. 

For all trials it contains defendant name, gender and age and occupation (if tagged in OBO); offence, verdict and sentence; and the OBO defendant ID

OBO offence, verdict and sentence data is simplified. In an OBO trial there may be multiple offences or outcomes per defendant; in order to flatten this, OBV data represents the most 'serious' offence and outcome (eg if sentenced to both imprisonment and a fine, it retains only imprisonment).

### data fields

* o2dtid - unique ID for data table (has no other meaning)
* obo_trial - OBO trial ID
* obo_deftid - OBO defendant ID
* sess_date - OBO session date yyyymmdd
* year - OBO session year
* trial_tagged - Whether the trial is tagged in OBC as containing speech (1=yes, 0=no)
* def_spk - Whether there is tagged defendant speech (short code): 1=yes, 0=no, NULL=no tagged speech
* speech - Whether there is tagged defendant speech ("deft_speaks", "deft_silent", or untagged trial="no_speech")
* trial_u_count - Count of OBC "utterances" (tagged trials only)
* trial_speech_wc - Total wordcount for OBC-tagged speech (tagged trials only)
* trial_total_wc - Total wordcount for trial report in OBO (all trials)
* deft_u_count - Count of OBC utterances by defendant
* deft_total_wc - Total wordcount for OBC-tagged speech by defendant
* deft_u_q - Count of questions asked by defendant
* deft_u_a - Count of answers by defendant
* deft_u_d - Count of defence statements by defendant
* deft_u_s - Count of other statements by defendant
* deft_given - Defendant given name (as tagged in OBO)
* deft_surname - Defendant surname (OBO)
* deft_gender - Defendant gender (OBO)
* deft_age - Defendant age (OBO) (NULL if no tagged age)
* deft_occupation - Defendant occupation as tagged in OBO
* deft_offcat - Offence category as tagged in OBO
* deft_offsub - Offence sub-category as tagged in OBO
* deft_vercat - Verdict category as tagged in OBO
* deft_versub - Verdict sub-category as tagged in OBO
* deft_puncat - Sentence category as tagged in OBO
* deft_punsub - Sentence sub-category as tagged in OBO


Words data
--------------

**obv_words_v2_28-01-2017.tsv.zip**

The OBC XML data was converted to tabular format (in a MySQL database) for data preparation. 

One row of data = one OBC tagged utterance (&lt;u&gt; tags). Please note that there are 217,000 rows of data and I cannot give any guarantees that your favourite spreadsheet software can handle this amount of data very well.

For the subset of single-defendant trials:

* the original speaker roles assigned in OBC were checked and corrected/filled in where necessary, particularly focusing on accurately identifying defendants. 
* broad speech categories were added to each tagged utterance: question, answer, defendant's defence statement; other statement

### data fields

* obv2wid - dataset unique ID
* sess_date - OBO session date
* year - OBO session year
* obo_trial - OBO trial ID
* obo_deftid - OBO defendant ID
* obc_u_no - OBC utterance number in trial
* obc_event - OBC event ID
* obc_speaker - OBC speaker ID
* obc_sex - OBC sex of speaker
* obc_hiscoLabel - OBC hisco data for speaker
* obc_hiscoCode - OBC hisco data for speaker
* obc_class - OBC hisco data for speaker
* obc_role - OBC speaker role
* obv_role - OBV speaker role: def=defendant; wv= witness or victim; lj = lawyer or judge; jur=juror
* words - text of words
* obv_words_type - OBV assigned words type: q=question; a=answer; d=prisoner's defence statement; s=other statement
* words_count - OBC word count
* defendant - name of defendant in trial
