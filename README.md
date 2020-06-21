# Implementation Notes 
### Variable Names and Brief Introduction

* Installed base of fixed-line telephone connections and teledensity <br>
  **fl_base_num, teledensity** <br>
  In principle, teledensity should equal to the number of installed base of fixed-line telephone connections divided by population as computed in 2004-2008. However, in 2009 and 2010, it is computed using the number of in-service base as numerator. Since I am not sure which one we should use in the study, I inlcude **fl_base_num_inservice** and **teledensity_inservice** corresponding to the in-service base of fixed-line telephone connections and teledensity. 
* Number of fixed-line telephone providers <br>
  **fl_provid_num** <br>
  I include **fl_provid** as a intermediate variable documenting all the fixed-line telephone providers to keep as much information as possible. 
* Number of mobile telephone providers <br>
  **mb_provid_num** <br>
  I include **mb_provid** as a intermediate variable documenting all the mobile telephone providers to keep as much information as possible. 
* Types of mobile technology available (e.g. GPRS, 1xRTT, 3G, etc.) <br>
  **mb_tech**
* Broadband Internet availability (number of providers and technology) <br>
  **bb_provid_num, bb_tech**
* Backhaul presence and speed if available <br>
  **bh_presence,bh_speed**
  It seems that backhaul is not available until 2010. I am not sure whether this is due to the lack of information or the backhaul actually strated to be available in 2010. 
