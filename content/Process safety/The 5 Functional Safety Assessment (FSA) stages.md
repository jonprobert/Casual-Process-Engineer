# Functional Safety Assessment

[Source](https://www.methodfs.com/functional-safety-lifecycle/functional-safety-assessments.php)

According to IEC 61511 the purpose of a Functional Safety Assessment (FSA) is to confirm that the “SIL has been achieved”. FSA are carried out at various stages of a project lifecycle to confirm compliance before moving on to the next stage.

The FSA should be delivered by someone not involved with either the delivery of the task or the verification of the task. Competence to carry out FSA requires a deep understanding of the requirements of the standard – this often means that FSA need to be carried out by 3rd party organisations.

IEC 61511 defines a number of “Stages” at which FSA should be carried out — these stages occur at key “hold points” within a project.

## The 5 Functional Safety Assessment stages

### Stage 1 - FSA1

**The Stage 1 FSA (FSA 1) is carried out once Hazard and Risk Assessment studies have been completed and the [[Safety Requirements Specification]] is written.**

==The FSA 1 is carried out before the SRS is passed to the “SIS Design” function – to ensure that the SRS is fit for purpose and based (amongst other things) on an appropriate level of diligence in the HRA studies.== It is self-evident that SIS Design shouldn’t start until there is confidence in the accuracy of the SRS.

Note that while IEC 61511 shows the FSA 1 as a single activity, on major projects the time elapsed between the initial hazard studies and issuing of the SRS could be significant – and if the FSA 1 finds an issue with the hazard study it may be entirely impractical to re-constitute the hazard study team after such a long time delay. For this kind of project it may be more useful to carry out the FSA 1 after each life-cycle phase, rather than waiting until the SRS is published.

A typical finding of an FSA 1 would be that the [[Hazard study 3|HAZOP]] Worksheets were not independently verified – they were instead checked by someone who attended the meeting. By attending the meeting, the person was therefore not independent. As this wasn’t recognised as a requirement at the time of the study, the study scribe did not add explanatory notes such that someone outside the study meeting could carry out verification.

### Stage 2 - FSA2

**The Stage 2 FSA (FSA 2) is carried out once the SIS Design and (if appropriate) the Factory Acceptance Test (FAT) have been completed.**

If a 3rd party Systems Integrator is being used, the FSA 2 is carried out before the panels are shipped to site.==The FSA 2 ensures that SIS design has been carried out correctly and that the FAT has correctly validated that the completed design meets the SRS.==

A typical finding of an FSA 2 would be that the 3rd party Systems Integrator did not have adequate Functional Safety Management procedures in place to ensure compliance with IEC 61511. In practice, this should have been confirmed before the Systems Integrator was awarded the contract.

### Stage 3 - FSA3

**The Stage 3 FSA (FSA 3) is carried out following Installation, Commissioning and final Validation (Site Acceptance Test) of the new SIS.**

==The FSA 3 is the final confirmation that “SIL has been achieved” and the SIS meets the requirements of IEC 61511 before handover to Operations.== The FSA 3 will also look in to the procedures and training for Operations and Maintenance and ensure that everything is in place. While the focus of the FSA 3 is on the installation, commissioning and site acceptance and “readiness” of the SIS, it is also required to look back at earlier FSA stages and ensure there are no open actions. The FSA 3 cannot be closed out until both FSA 1 and FSA 2 are also closed.

A typical finding of an FSA 3 would be that the installation team produced “red pen” drawings that were passed to the drawing office for “as built” documentation to be developed, but the changes noted on the “red pen” drawings were not subject to adequate Management of Change for Safety Instrumented Systems.

### Stage 4 - FSA4

**The Stage 4 FSA (FSA 4) is carried out at defined intervals to look in to the functional safety activities of the (ongoing) Operation and Maintenance (O&M) of the SIS.**

==The FSA 4 will review O&M procedures and training, will examine the approach to proof testing and inspection and assess the collection and analysis of SIS performance data.== The frequency with which FSA 4 should be carried out is not defined in the standard, but good practice would be to carry out the first FSA 4 immediately after the first round of proof tests for a newly installed SIS (typically a year after commissioning) and then to repeat the FSA 4 on the same time period as the hazard study re-validation (typically every 5 years).

A typical finding of an FSA 4 would be that Instrument Technicians have not been correctly reporting failures found on proof tests and instead have simply “fixed” all faults found. The result being that dangerous undetected failures of the SIS have not been correctly treated as “near miss”.

### Stage 5 - FSA5

**The Stage 5 FSA (FSA 5) is required when a Modification is made to a SIS.**

The FSA 5 is carried out in two parts. ==The first part assesses the plan for the Modification – and determines if the approach is adequate for the given change. The second part assesses whether the implementation of the Modification correctly followed the intended plan.==

A typical finding of an FSA 5 would be that a change made to a SIS Application Program was not tested in such a way that any unintentional changes to other parts of the program would have been detected.