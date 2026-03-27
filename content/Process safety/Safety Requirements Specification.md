# Safety Requirements Specification

[Source](https://www.methodfs.com/functional-safety-lifecycle/safety-requirements-specification.php)

The Safety Requirements Specification (SRS) is one of the key documents for delivering functional safety.

Below is a list of the other lifecycle phases that depend materially on the availability and quality of the SRS:

- **SIS Design** – it’s self evident that designing a SIS is only possible if the requirements of the SIS are defined. The SRS is the document that provides that definition.
- **Validation** – whether at Factory Acceptance Test (FAT) or Site Acceptance Test (SAT), since the objective of SIS Validation is to confirm that the design meets the requirements, it is necessary to have a comprehensive definition of the requirements so that validation - that the SIS meets those requirements - can be carried out.
- **Developing Proof Tests Procedures** (PTP) – we could think of the annual proof test as a repeated validation test, so again having the SRS available would be a pre-requisite for developing the PTP.
- **Authoring Operations and Maintenance Procedures** – describing how the operators will interact with the SIS can be most easily developed from the content of the SRS.

The SRS would also be a typical input into any Modification (what are we changing in the specification?) and any review of a SIF demand (did it work as it was supposed to?).

The SRS also provides a signpost to other key documents related to the SIS. The SRS should reference “down” to the tags of the SIF components and “up” to the Hazard and Risk Assessment documentation. It should be possible to use the instrument tag to locate the particular SRS that describes the need for that particular instrument. And from the SRS you should be able to find the LOPA scenario that concluded a SIF with a given RRF was needed. And from the detail in the SRS you should be able to find the lines in the [[Hazard study 3|HAZOP]] worksheet that identified the initiating events that could bring about the harmful event that the SIF is protecting against.

It is very likely (despite what the idealised safety lifecycle might suggest) that the SRS will be updated through the SIS design process (as the design and the specification of the design evolve together. And the SRS will be updated again, once the instrument tags are known (towards the end of the design process) and following Modifications, re-validation of Hazard and Risk Analysis documentation and re-visiting other lifecycle activities.

The Safety Requirements Specification could be considered to have 4 main sections:

- **Integrity Requirements** – how “safe” does the SIF need to be? (What is the SIL? what is the required PFD? what is the mode of operation (based on the demand rate)?
- **Functional Requirements** – what is the SIF supposed to do? (What does it sense? What is the trip point? what does it actuate to bring about the safe state? how fast does it need to act?).
- **Operations and Maintenance (O&M) Requirements** – what features do we want (and not want) to add to the design to make O&M activities efficient, effective and safe?
- **Security Requirements** – an evolving area, but clearly we need to make our SIS secure, otherwise we can’t be sure it’s safe. And this includes both physical security as well as cyber.