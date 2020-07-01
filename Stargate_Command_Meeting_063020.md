## Stargate Review meeting from June 30, 2020

**Zaki Manian(Iqlusion):** Where we are and what risks are there?  We’ve made really good progress on reducing risks for the last two weeks.

## Risks to the success of Stargate

### Blockchain pruning feature problems

From v0.38 with hard work from Bez & Eric. Pruning system is nearly done and stable as in 0.37.

### Upgrade capability in the CosmosHub

Upgrade capability will be deployed in the Stargate upgrade. It benefits from the existence of an external management process maintained on the Regen github. Now we are upstream the upgrade manager into the Cosmos SDK repo where it will be maintained. This is in progress and the risk of the upgrade capability is receding.

## Action Plans & Deliverables: Next 2 weeks and single largest surface area of breakage

1. Changes to signature system

2. Changes to query to use gRPC protobufs and gRPC proxy

### Questions on the Action Plans & Deliverables

**All in Bits:** Let’s make sure this is transparent to the community.

**Zaki Manian(Iqlusion):** Yes, all content will be freely republishable and disseminated.

**Zaki Manian(Iqlusion):** One of things that will happen during the testnet will be an upgrade of the testnut hub so that we’ll experience how it impacts the open IBC channels. Let’s experience as validators, operators and developers, what does an upgrade feel like with the upgrade manager.

* Planning

* Testnet

* Awareness

* Integration process status

**Gregory Landua(Regen Networks):** We want to ship 0.39 as well-tested piece of software for the community. We have lots of coordination and synergy. It’s an ecosystem approach to testnets. We will test SDK upgrade with multiple chains participating together. We should have an in-depth in the process and harmonize. Let’s step back and engage with other ecosystem partners so that we can make sure the validates are not overloaded. Let’s create a coherent narrative of interchain upgrades. This is the first time we are approaching interchain upgrades. Ethan will be the point person on the testnet side. We want to do lots of good coordination and have a rhythm of things. Example: What would it look like for an incentivized testnet for the SDK? We don’t want an incentivized testnet. We also don’t want Regen to be carrying the incentive layer alone. Let’s seek strong synchronization.

**Tess Rinearson(Interchain Berlin):** Want to make sure the piece of the puzzle works well.

**Zaki Manian(Iqlusion):** Primary need Starget focus: Reality is that no one conducts integration testing against anything other than a public testnet. We want to have a target for integration testing facilitation. We have lots of other needs & use cases. This will be a post-release testnet. We may want to do something like Regen has done on their testnets.

**Gregory Landua(Regen Networks):** 0.39 testnet first, then run a Stargate integration testnet. These are topics that require some deep conversation and multiple opinion. We should clarify scheduling and timing so we know what we test and when.

**Zaki Manian(Iqlusion):** The project plan will lead to the governance proposal. The Hub will feel confident with the risks associated with the upgrade.

**Taariq(Iqlusion):** From what we’ve put together documentation for the governance proposal will come after we have collected the testnet results, and any required changes from all participants.

**Zaki Manian(Iqlusion):** We went through this acceptance testing process and why we think we can upgrade

**Gregory Landua(Regen Networks):** I really want to fix in on what is the criteria this group thinks is needed for the release candidate. What level of testing are we trying to pass the baton on for the subsequent integration testing and Hub focused testnets. If I can fix the criteria, then I can back-cast to Tess and the Tendermint team. It might give us more of a timeline. Do we want this release candidate tested completely? I don’t want to presume that.

**Zaki Manian(Iqlusion):** One of things that we learned from the Game of Zones process is that the Software development process is functioning well. We had two issues during Game of Zones that uncovered 5 lines of code fixe that took 24 hours to resolve. The question is maybe not what will work. I think we don’t need to do something unique or special that we haven’t done for other releases. The quality assurance processes we have been running have not degraded since we launched the hub.

**Christopher Goes(IBC):** My evaluation of Game of Zones. Our individual software QA proc3sses were fine, but we did not have a good story of how the changes were ported downstream to Gaia. We also did not have a good story of the upstream changes were communicated. Currently, no one has the Gaiai contract. Iqlusion and Zaki is leading Stargate, but it’s not clear what the IBC team is responsible for. It’s good to have some clarity.

**Gregory Landua(Regen Networks):** Seeking level of clarity and synchronization so that we know where things get pushed.

**Zaki Manian(Iqlusion):** Let me explain how this should run for Stargate and then discuss further existential views. I’m expecting that there will be a process of porting the state of sim app to Gaia for the purposes of facilitating a testnet upgrade. Zaki is expecting that this will be in the capabilities of Zaki, Taariq, ambient engineering team to help facilitate the process. Zaki will own the process to get Gaia up to sim app.

**Billy Rennekamp(ICF):** Let’s check the temperature on ambient developer capability and availability to kdo this work. Marco or Alessio?

**Christopher Goes(IBC):**  This the phase of the Gaia tesnets. These are the people leading. We need some type of project management for these testnets.

**Sam Hart(ICF):** We should really make sure that although Iqlusion is leading project management, ambient resources and developer requirements are accounted for explicitly.

**Zaki Manian(Iqlusion):** We want to have a Gaia that depends on 0.39. Zaki does not have a good understanding of magnitude of the change. It’s mostly QA and then fixing whatever bugs that are the result of the QA process. It will be a couple of days of work that Zaki anticipates as the magnitude.

**Christopher Goes:** The IBC team is capable of leading testnets, helping with testnets and executing delegation. The concern is only for project management so that it doesn’t fall through the cracks.

**Zaki Manian(Iqlusion):** Does the IBC team have the capacity for planning the upgrade process for running networks that. Zaki wants to do more than one upgrades with IBC active on these tesnets. Simulated upgrades will help us build expertise to handle whatever is neded, including security vulnerabilities and chain halts so that we build community experience.

**Christopher Goes:** We can do the above.

**Zaki Manian(Iqlusion):** High level understanding of the scope of required. Then the understanding of the planning from the Upgrade Manager to the IBC process. We want to do a network upgrade and have IBC survive. We will do small simulations. We will do this on the Stargate network to towards the end of the integration testing phase. We will do a simulated upgrade that won’t be API breaking.

**Christopher Goes(Interchain Berlin):** IBC upgrades are difficult because there will be many chains. We might QA test IBC version changes. IBC team can test that related stuff on Gaia. We can summon into existence a document that outlines who is doing what testing and when so that they can sign off.

**Marco(ICF):** The current Gaiai master will be reverted back to the last release. Ran into some panic issues and revert to the previous release for Gaiai master. Alession and Jonathan would have the best insight.

**Alessio Treglia(ICF):** We may not want to keep Gaia in sync with SDK. We accrue technical debt. Maybe having a branch that will be open and kept buildable against the latest SDK. It is good exercise to keep it in sync. Trying to upgrade with the latest SDK is a good way to spot bugs.

**Zaki Manian(Iqlusion):**  More imagining what we did with Game of Zones. Let's not try to keep them in sycn. Let these big meta issues, especially during this phase. It's enormously painful and especially painful. Keeping it in sync means syncing to these intermediate designs that are not designed to be a coherent picture. Keeping it in sync with Gaia will be very expensive with QA impacts. The yield will be increased familiarity with all these pieces. Zaki will get into the code and work to battle panics and testnets. It will yield a better understanding of what has happened.

**Christopher Goes(Interchain Berlin):** Quick logistical question: Do we have the right communications channels for Stargate?

**Zaki Manian(Iqlusion):** Primarily working through the public Discord channel has been working well. We'll need to spinup a separate communication channel for the champion integration partners. We could potentially talk to them. Zaki and Taariq will be the firewall. We don't want to repeat throw engineers into an exchange communications channel and try to service their issues. Getting that more orgnaized was always a goal.

**Billy Rennekamp(ICF):**  When should we expect the first markdown update? What sort of cadence should we be using?

**Zaki Manian(Iqlusion):** Let's talk with Taariq before we commit to something.

**Tess Rinearson(Interchain Berlin):** Thanks for the firewall analogy. Two quick questions for Zaki. The estimated date for the testnet. July 27th was the date prposed. Can you show the timelines that will get us to that point so that all the requisite pieces are on track.

**Zaki Manian(Iqlusion):**  Yes. We'll put that all together. Giving dates for anything is dangerous. All these organizations need a resource with some timeline to operate. I don't view the deadline of July 27th as a hard deadline. We'll keep updating it. I'm expecting the Tendermint team will cut their 0.34 RC and spin up testnets. They will be mostly in the role to support the SDK and upstreaming their changes and then supporting Gaia and upstreaming their changes.

**Tess Rinearson(Interchain Berlin):** That's right. It's good to set a target to shoot and very useful. Just want to know where we are in the timeline as a form of communication.

**Zaki Manian(Iqlusion):**  The IBC changes are well under control. What's happening on the Tendermint side is under control. The discourse and conversations in various software channels sound like that we are landing all the changes to the signature system. The changes to the query system seem emininent. The risk that Zaki called out at the beginning of this meeting are big timeline risks.

**Tess Rinearson(Interchain Berlin):** Have we agreed whether LaunchPad is a thing and exactly what it is?

**Billy Rennekamp(ICF):**  We have a call on Friday to discuss LaunchPad.

**Zaki Manian(Iqlusion):**  Launchpad is a consequence of Stargate, but not part of the Stargate upgrade. Writing a spec for what is LaunchPad is out of scope. It's good to define and keep a mental model: We have alot of people who care about the software, but Stargate is concerned with Exchanges, Wallets, Block Exlporers, and Validators. There are Developers and Zones who are interested partners, but they are not the primary objective of Stargate. LaunchPad is an effort to take care of them.

**All** Bye.
