# CR 13954681: LHG: DCS-CM: Standby Acceptance & Regrade Activity Overview Lists

This document describes the technical details of the redesign of the CM solutions for CR 13954681. The technical work is divided into three parts.
In each part, the current and new solution will be described.

*This text will be italic*
_This will also be italic_


# Part 1.  Service Migration
#### A new directory 'ngosl' has been created to store the data, which is currently stored in nglst.
* The migration includes
  * Edifact message: CFNDRQ
  * Backend service: SvcFnd, SvcFndPreview
  * Regression testing files: ngoslrgr/oslEdi/
    * FndAcs_StandbyAcceptRegrade_Overview.Case_001.scn
    * FndAcs_StandbyAcceptRegrade_Overview.Case_002.scn
    * FndAcs_StandbyAcceptRegrade_Overview.Case_003.scn


> Status:  The migration of Edifact message and backend service has been done.  Regression testing is still in progress. 


# Part 2.  Dependency removal
#### Current dependencies are listed under ngosl/Deps, unrelated dependencies need to be removed in ngosl without any impact.
ngbzr       headers  
ngflipub    headers  
ngoslpub    headers  
...  
...  
...  
ngahu       headers  
ngcpm       headers  
ngcrp       headers  

> Status:  The work is not started, because it can't be started until the Part 1 is finished.


# Part 3.  CHDWRQ parallel asynchronous calls.
#### CHDWRQ is being called in a synchronous way
