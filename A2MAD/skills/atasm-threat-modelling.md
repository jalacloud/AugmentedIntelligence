# Threat Modelling

## **What Is Threat Modeling?**

Threat modeling is an analysis technique often employed to identify the security needs of a system. As such, threat modeling is often undertaken while designing software and digital systems; threat modeling must be considered a foundational technique underlying software security, and in particular, secure design. Threat modeling is a key technique for software security’s associated development processes and strategies, the Security Development Life cycle (SDL) also called the Secure Software Development Lifecycle (S-SDLC).

Sometimes, systems are deployed without a threat model. In these cases, system stakeholders may choose to build a threat model post-release to identify any security weaknesses or un/under mitigated risks that are already in service.

In either case, the threat model’s output offers software makers a set of implementable improvements designed to improve the overall attack resilience and compromise survivability of the target system and its stakeholders.

Threat modeling can be defined as, “*a technique to identify the attacks a system must resist and the defenses that will bring the system to a desired defensive state*[[1]](https://brookschoenfield.com/?page_id=341#_ftn1).”

The definition highlights a few key points. First, threat modeling is not a design or an architecture, it is an analysis technique. Next, its purpose is to identify attacks and defenses. Third, and this is key, the defenses bring the system to its “desired defensive state.” That is, the object is not to bring the system to an ivory tower security perfection (which, of course, doesn’t actually exist in the real world, anyway).

In order to complete a threat model, one must first understand what defensive state a system’s stakeholders expect the system to achieve. To put that in a different way, *a priori* to analyzing the attacks and specifying the defenses, the analyst must understand against what the system must defend and to what level—what is commonly termed its ‘security posture.’… From the understanding of stakeholder risk tolerance, one may then derive the security posture of a system, its “desired defensive state”—that is, the appropriate defenses that will resist those attacks against which the system and its stakeholders will defend.”

The primary output of a threat model undertaken as a software design activity must be a set of defenses that taken together provide sufficient protection to the needs of the system’s stakeholders. Since risk tolerances and relevant threats are organizationally and system dependent, there is no “perfect” set of defenses for every situation. Brook will base defense findings on industry best practices, as given by publications such as National Institute of Standards and Technology (NIST) security publications and/or customer standards and policies, as required.

## **Types of Threat Models**

There are three general objectives derived through threat modeling:

1. To improve the security architecture and design of a target system, organization, process, design, concept, or architecture.
2. To identify significant attack scenarios and their potential impacts
3. To precede penetration testing as a guide to identify the most impactful areas for testing

Models generated to improve design (the first case, above) will also fulfill the requirements of the other types. A threat model for secure design is a superset of the other two, risk enumeration models are a superset of a model to guide testing.

The deliverables from a threat model intended to improve secure design were set out above.

The deliverables from a threat model intended for identifying risk might not contain mitigations, while a model for the purposes of guiding security verification generally focuses on identifying a comprehensive list of attack possibilities. The test will then validate each attack possibility.

## **Threat Model Contents**

The following list sets out the various artifacts and explanations that customers may expect from a threat modeling exercise:

- A demonstrated understanding of the architecture of the target system (software, organization, process, technology, application, etc.). Usually the architecture will be expressed through an architecture diagram, as well as a set of statements. The system’s major functional components and data flows with other systems, users, and internal flows will be shown in the diagram and explained. Where varying levels of component or system trust exist, trust boundaries will be depicted on the architecture diagram. Customer may supply an architecture diagram. Brook may need to annotate or otherwise change the diagram for the purposes of threat modeling
- Both organizational purpose(s) and the purposes of the technologies will be described
- A description of the existing security controls and strengths of the system
- The highest sensitivity of data in each data flow or exchange, and of each data at in permanent storage
- Any boundaries separating areas, zones, and components whose level of system trustworthiness is higher than others taking part on the exchange (trust boundaries)
- An enumeration of every credible attack scenario[[2]](https://brookschoenfield.com/?page_id=341#_ftn2). “Credible” means that there is or will be an active threat agent who has one or more capabilities to carry out the exploitation and a believable path to deliver that exploit. Attack scenarios will be paired with attack surfaces, points on the system that are exposed in some manner to attack and through which an attack scenario can be started.
- The exploit must correspond to a weakness that currently exists or that has occurred in similar systems and technologies in the past that can or has been leveraged by an attacker. Successful exploitation must deliver one or more gains or steps towards the threat agent’s goals. Attack scenarios are catalogued irrespective of the level of existing defense against each attack. Please see “Defenses”, below
- Each attack scenario will be rated for risk (please see the section on risk in this document) “Risk” is taken to include the potential for significant harm (impact) to any of the system’s stakeholders
- For every attack scenario that is deemed to be un/under-mitigated, one or more defenses that will reduce risk to acceptable levels based upon industry best practice and customer standards (if any) will be suggested.
- Attack scenarios that the system’s existing defenses mitigate sufficiently to customer requirements will be included in a comprehensive threat model analysis
- An architecture diagram (as described previously) amended with the attack scenarios and defenses labeled

## **Threat Model Philosophy**

“*The analysis that leads one to the contextually relevant attacks, let’s call that “threat modeling” for the sake of discussion, is best done as an early part of any development process, as well as being an ongoing conversation as architectures, designs, and implementations evolve. Certainly, there is very little that an architectural risk assessment of a system can do if the system cannot be changed*.”[[3]](https://brookschoenfield.com/?page_id=341#_ftn3)

Brook brings to each analysis an ongoing study of active threat agents, their goals, their tactics, techniques, and processes (TTP), and their risk tolerances, in other words, threat agent profiles.

Brook brings a working knowledge of cyber-risk, in order to generate consistent, repeatable risk ratings. Please see any of his risk-related public presentations, or Chapter 4 in *Securing Systems* for additional information about risk rating based on Factor Analysis Of Information Risk, an Open Group standard.

Brook uses first-hand knowledge of technology, architecture, and use-case specific attack types to derive the set of appropriate attacks for the system under analysis[[4]](https://brookschoenfield.com/?page_id=341#_ftn4). Brook may also make use of other methods and resources in order identify that particular set of attack scenarios which have significant likelihood of attempt and if successful would result in significant harm to the system’s stakeholders. Some example resources that might be employed include:

- Microsoft’s STRIDE (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege). If a customer requires the use of STRIDE, potential harms could then be described with Microsoft’s DREAD (Damage, Reproducibility, Exploitability, Affected users, Discoverability), if needed
- MITRE’s ATT&CK database and organization of known attack techniques
- MITRE’s CAPEC (Common Attack Pattern Enumeration and Classification)
- MITRE’s CWE (Common Weakness Enumeration)[[5]](https://brookschoenfield.com/?page_id=341#_ftn5)

Every threat model is generated through an appropriate skillset matched to the technologies to be encountered in the analysis. Potentially, subject matter experts (SME) for specialized technical domains may also be consulted to ensure that each threat model is comprehensive and appropriate to the system and client under analysis.

## **Threat Model Background Knowledge**

A threat model must be considered within its business, deployment, and execution context. The high-level knowledge sets are given in the following graphic[[6]](https://brookschoenfield.com/?page_id=341#_ftn6). Understanding contextual knowledge is critical to generating a threat model for any purpose (please see below) that is grounded in existing capabilities and requirements, grounded in the realities of each customer situation.

![2.3 3 eses grey.jpg](http://brookschoenfield.com/wp-content/uploads/2020/08/2.3-3-eses-grey-1024x490.jpg)

Threat model pre-requisite information

While somewhat creative, a threat model must be grounded in hard data. Obviously, those active attacks that can be exercised against the system under analysis will be applied.

Furthermore, an analyst also applies relevant past exploit/vulnerability pairs even if such vulnerabilities have not yet been found in the system. It’s important to understand that even the most rigorous testing, as Edsger Dijkstra so famously quipped, “proves the system has bugs, not that it doesn’t.” If there have existed exploitable vulnerabilities in any component within the system under analysis, even though fixed in the versions included, then the analysis must assume that at least some similar issues will likely be found in those components at some point in the future.

An analyst may stop enumerating attacks when:

- The attack scenarios seem demonstrably more complex than other methods of compromise that are easier and more readily available.
- The required preconditions to an attack scenario lie well outside the range of normal or typical configuration and usage.
- Significant inside assistance (for externally-originated attacks) is required to proceed. (Insider threat is a special category that requires careful analysis across an organization. It rarely should be tackled one system analysis at a time. Separation of duties are often determined on a per-system, per-function, or per-privilege basis.)
- Where no exploit exists for a particular vulnerability, or the vulnerability is not exposed for remote exercise or research (it’s important to periodically revisit the threat model in light of new developments).
- Attack scenarios start to border on the ridiculous, the strained, or the dubious, or depend upon computer technologies that have yet to be invented (i.e., “science fiction”).

An analyst may stop specifying defenses when:

- Each defense has some overlap of protection with at least one other defense
- Each significant attack vector is covered at least partially by more than a single defense (see inset)

For more stringent security postures, each attack scenario must be mitigated. “Significant” is meant to mean those attack vectors whose successful exercise will cause significant harm. It also implies attack vectors that are considered “credible”—that is, there is sufficient evidence that the attack vector can be exercised by an active threat actor should a weakness that can be exploited be released or reach production.”

## **Threat Model Process Armature: ATASM**

At the highest level, an assessment follows the mnemonic, ATASM:

**Architecture** ? **Threats** ? **Attack Surfaces** ? **Mitigations**[[7]](https://brookschoenfield.com/?page_id=341#_ftn7).

![](http://brookschoenfield.com/wp-content/uploads/2020/08/2.1-ATASM.jpg)

Figure 1: ATASM

The architecture must be understood sufficiently in order to enumerate the attack sur- faces that the threats are applied to. Applying specific threats to particular attack surfaces is the essential activity in a threat model.

The architecture analysis will uncover:

- The system’s technology components and logical functions
- The interactions (flows) between components and functions
- The uses and use cases to which the system will be put
- The assets requiring protection and the assets that may be targeted by the appropriate range of attackers

Since ATASM provides a high-level, process armature for threat modeling, any threat model analysis may also employ other well-known methods that customers may need such as STRIDE[[8]](https://brookschoenfield.com/?page_id=341#_ftn8), P.A.S.T.A.[[9]](https://brookschoenfield.com/?page_id=341#_ftn9), VAST[[10]](https://brookschoenfield.com/?page_id=341#_ftn10), Trike, and other approaches and techniques.

While ATASM provides an overarching framework to a threat model, a technique like STRIDE may be used to build the appropriate collection of attack scenarios. (Please see Risk Rating for a discussion of DREAD) There is no tension between ATASM and other threat modeling techniques; ATASM is intentionally inclusive. Other techniques tend to focus on a specific part of a complete threat modeling analysis, and then describe how a thorough analysis proceeds, ending up essentially describing ATASM.

Before beginning an ARA and threat model, one will need to have examined the current threat landscape into which the system will be deployed. Further, investigation will have taken place to understand the risk posture of the organization that will use and deploy the system as well as what the overall risk tolerance of the organization is. One must under- stand the current state of security capabilities and infrastructure in order to understand what controls are easiest to implement and what will be a future state (perhaps only a wish?). Since no security is perfect, there will be limitations that must be taken into account. Certain approaches or security technologies may be impossible, given the cur- rent state of affairs. If the assessor wants to provide real-world mitigations, she or he will need to know what can and cannot be accomplished in the present, in the short term, in the medium term, and perhaps longer still. Each execution environment typically presents a unique set of security services and a unique set of vulnerabilities and security challenges. A system may take advantage of the services but, likewise, must take account of the runtime’s weaknesses. Finally, as was noted previously, different deployment models require different architectural approaches to security. Customer premise equipment must be capable of implementing the owner’s security posture. Systems destined for an infrastructure that is controlled by an organization will inherit that infrastructure’s security weaknesses and strengths.

| Strategy | Threat landscape | Risk posture |  |
| --- | --- | --- | --- |
| Structures | The set of possible controls | Existing security limitations |  |
| Specifications | Data sensitivity | Runtime and execution environments | Deployment models |
- Runtime models
- Deployment
- Deployment processes

The security analyst will arm her or himself with sufficient background knowledge to thoroughly assess a system. The enumerated background subjects create a strong basis for threat modeling.

![A close up of text on a white background Description automatically generated](http://brookschoenfield.com/wp-content/uploads/2020/08/5.2-ATASM-Procedure-Steps-791x1024.jpg)

Figure 2: ATASM Sub-tasks

Figure 2 orders those steps by the high-level ATASM abstraction. That is, architecture steps are followed by threat-related tasks. The results of these are applied to an enumeration of attack surfaces, which, when prioritized, can then be defended by building a set of risk mitigations, a defense-in-depth of security controls.

“Threat” is a highly overloaded term with information security; it carries a number of overlapping, even conflicting definitions. For the purposes of ATASM, “threat” is meant to encompass an attack’s profile including:

- Active threat actors
- Threat actors’ goals[[11]](https://brookschoenfield.com/?page_id=341#_ftn11) and those goals applicability to a particular system
- The Tactics, Techniques, and Processes (TTP) threat actors will employ
- Threat actor technical capability and sophistication
- Threat actors’ risk tolerances
- The amount of effort each threat actor will habitually put into attacks for a particular purpose

In order to produce a threat model grounded in the realities of the current “threat landscape”, understanding of each gross type of threat actor’s profile is essential to understand how a system will be attacked. Attack surfaces are potential entryways into a system exposed to threat actors’ capabilities. These are usually data entry points and points of human interaction with a system. Inter/intra-system communications often present attack surface.

Mitigations are those defenses which have already been built into the system at the time of analysis, if any.

Each of Figure 2’s sub-tasks will then be broken down into its constituent steps. The breakdown into sub-tasks is not arbitrarily infinite[[12]](https://brookschoenfield.com/?page_id=341#_ftn12). Still, there are a number of steps to, for instance, understanding a logical and component architecture.

Another way of looking at the threat modeling process is to see it as a set of inter-related and intertwined analyses. As David Wheeler (Author and Principal Engineer, Intel) once said to Brook, “It doesn’t matter at which activity one starts, so long as one completes all of them.” Below is Dave’s “circle of threat modeling”, as drawn by Sung Lee (Senior Security Architect, Intel):

![A close up of a logo Description automatically generated](http://brookschoenfield.com/wp-content/uploads/2020/08/Slide1-961x1024.jpeg)

Threat model activity circle

The relationship between the analyses that must be performed isn’t circular, and certainly must not be considered linear. Each activity intersects with, has dependencies from, and will be transformed through information and learnings derived from the other topics of analysis. A change of assets may change the architecture and vice versa. Most likely, structural changes will involve a changed set of attack surfaces and their related mitigations. A new use case may open up new opportunities for threat actors, thus expanding the attack surface. And so on. Hence, the following diagram may better represent the non-linear, and inter-dependent set of activities that must be completed for a threat model:

![A close up of a logo Description automatically generated](http://brookschoenfield.com/wp-content/uploads/2020/08/Slide2-1024x821.jpeg)

Attack and defense investigation are typically performed through architecture analysis and decompositions into a system’s constituent components. Decomposition is a technique used to enumerate those entry, exit, and execution points at which a system may be attacked (“attack surfaces”), and the places within the system’s structures where defenses may be implemented (“defensible boundaries”). Unfortunately, the amount of decomposition that will need to be performed is highly dependent upon an architecture and its runtime context. This is because attack methods vary depending upon architecture and execution technologies.

At the risk of ordering an analysis that typically benefits from flexibility, and may, in fact, as well-known threat modeler, Gary McGraw, PhD, likes to say, “is fractal”, generally, the following high level steps will be taken, though not necessarily in such a strict, linear fashion:

1. Architecture and Artifacts
    1. Understand the Logical and Component Architecture of the System
    2. Understand Every Communication Flow and Any Valuable Data Wherever Stored
2. Threat Enumeration
    1. List All the Possible Threat Agents for This Type of System
    2. List the Typical Attack Methods of the Threat Agents
    3. List the System-Level Objectives of Threat Agents Using Their Attack Methods
3. Attack Surfaces
    1. Decompose (factor) the Architecture to a Level ThatExposes Every Possible Attack Surface
    2. Filter Out Threat Agents Who Have No AttackSurfaces Exposed to Their Typical Methods
    3. List All Existing Security Controls for Each AttackSurface
    4. Filter Out All Attack Surfaces for Which There IsSufficient Existing Protection
4. Data Sensitivity
5. Risk rate and prioritize
6. Possible Controls
    1. Apply New Security Controls to the Set of Attack Services for Which There Isn’t Sufficient Mitigation
    2. Build a Defense-in-Depth

## **Analysis Constraints**

The constraints within which attack enumeration must be made are as follows:

- The risk tolerance of the organization owning/fielding the system
- The risk tolerance of the system’s users (if any)
- The capabilities, goals, expended effort, and risk tolerances of the enumerated set of threat agents who will wish to attack
- The trust/risk profiles of the system’s components, including infrastructure(s) and external entities
- The runtime/execution environment(s)
- The existing defenses (including infrastructure defenses and services)
- The highest sensitivity of data flowing through and being processed
- The probability of a particular attack scenario being low enough to be discounted

## **Rating Risks**

Only the customer can decide which risks are acceptable and which must be mitigated. Indeed, the selection of risk treatments, and at what level of mitigation is tolerable must remain a customer decision. Brook will suggest risk treatments based upon industry standard practices and the risk tolerances that have been identified during analysis.

Where customers can articulate customer standards, he will identify those defenses and mitigations that he believes will bring threats within customer toleration.

Threat model risk ratings can be based on The Open Group’s Factor Analysis of Information Risk (FAIR) standard. A lightweight method suitable for multiple, rapid assessments based upon FAIR then is used for threat modeling, Just Good Enough Risk Rating (JGERR)[[13]](https://brookschoenfield.com/?page_id=341#_ftn13), as described explicitly for threat modeling in Chapter 4 of *Securing Systems*. If desired, risks identified through a threat model may also be rated using Microsoft’s DREAD rating method. JGERR and DREAD are complimentary approaches and may be used in conjunction.
