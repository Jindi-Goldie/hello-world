# Implementation Notes 
### Variable Names and Brief Introduction

* Installed base of fixed-line telephone connections and teledensity <br>
  **fl_base_num, teledensity** <br><br>
  In raw data, the variable names for fl_base_num are *acessosfixos* in 2004 and 2005, *acessosinstalados* in 2006 and 2007, *accessosfixosinstalados* in 2008 and 2009. This variable is missing in 2010.  <br><br>
 The variable name for teledensity is *teledensidade* in all years. <b>However, the definition of teledensity is not very clear.</b> In principle, teledensity should be equal to the number of installed base of fixed-line telephone connections divided by population as computed in 2006 and 2007. However, in 2009 and 2010, it is computed using the number of in-service base as numerator. The two variables are only missing in 2010. Since I am not sure which one we should use in the study, I inlcude **fl_base_num_inservice** and **teledensity_inservice** corresponding to the in-service base of fixed-line telephone connections and teledensity. These two variables are missing in 2004 and 2005. <br><br>
  To my surprise, both the number and the density declines overtime. I am not sure whether this is in accordance with what happens during that time. 
 <br><br>
* Number of fixed-line telephone providers <br>
  **fl_provid_num** <br><br>
  I include **fl_provid** and **fl_provid1-fl_provid37** as intermediate variables documenting all the fixed-line telephone providers to keep as much information as possible. <br><br>
  In raw data, the variable names for fixed-line telephone providers are *espelho* in 2004 and 2005, *autorizada* in 2006 and 2007, *operadoras* in 2008, 2009 and 2010. <b>However, There is another variable named *incumbent* in data from 2004 to 2007 and there is only one company name under that variable. I find the company there very similar to that in *espelho* and *autorizada* and if we do not counting it, many municipalities would have no fixed-line providers</b>. I am not sure whether we should count that company when computing the number of providers. I temporarily count it as one provider and if that is not correct, I also include a variable named **fl_provid_num_noincum** without counting it. 
  
* Number of mobile telephone providers <br>
  **mb_provid_num** <br><br>
  Similarly as in the fixed-line, I include **mb_provid** and **mb_provid1-mb_provid6** as intermediate variables documenting all the mobile telephone providers to keep as much information as possible. <br><br>
  In raw data, the variable names for mobile telephone providers are *operadoratec* in all years. I also include four dummy variables(*mb_provid_GSM mb_provid_TDMA mb_provid_CDMA mb_provid_A*) indicating whether a certain technology is used in the municipalities. However, the technology is missing in 2008, 2009 and 2010.
  
* Types of mobile technology available (e.g. GPRS, 1xRTT, 3G, etc.) <br>
  **mb_tech** and dummy varibles: **RTT GPRS iDen Edge EVDO WCD HSPA WCDMA** which equals to 1 if that technology is available. <br><br>
  In raw data, the variable name for mobile technology are *redededados* from 2005 to 2009 and *dados* in 2010. This variable  is missing in 2004. I also include **mb_tech_num** documenting the number of the mobile technology available.
  
* Broadband Internet availability (number of providers and technology) <br>
  **bb_provid_num, bb_tech_num** and dummy variables: **bb_CM bb_C bb_A bb_M** <br><br>
  In raw data, the variable name for broadband is *bandalarga* in all years. However, although there are no missing values in provider names, the information about technology are missing in 2009 and 2010. I considered using the match between provider name and technology in previous years to make up for this, but it seems that the provider names do not uniquely match to a single technology. 
  
* Backhaul presence and speed if available <br>
  **bh_presence,bh_speed** <br><br>
  It seems that backhaul is not available until 2010. I am not sure whether this is due to the lack of information or the backhaul actually strated to be available in 2010. 
  In raw data, the variable name for backhaul presence is *backhaul* and *bandabackhaulmbps8* for backhaul speed.
  
### Merge of Dataset
The time variable in the cleaned panel dataset is **year** and the individual variable is **muni**. <br><br>
There is no munipacity number in the raw data of 2010 and there are some repeated observations (10 in total) of the same munipacity in 2010. The information in the repeated observations are basicly the same except few variables like types of mobile technologies. I temporarily kept the first one of the repeated observations to make it a panel data. I merged the 2010 data to the munipacity_number-location_sigla data using both the sigla and location and there are 179 observations that can not be matched. I am not sure whether this matters in our study and I will have a closer look at the matching process if needed. 


