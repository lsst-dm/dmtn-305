# Rubin Science Platform issue tracker: roadmap and topics for further discussion

```{abstract}
Background and context for this work; why JIRA Service Desk; technical and policy questions; topics needing discussion.
```

<!-- ## Add content here

See the [Documenteer documentation](https://documenteer.lsst.io/technotes/index.html) for tips on how to write and configure your new technote.
 -->
## Programmatic Notes

(This section is only of interest for historical context and traceability)

The (then LSST) Construction MREFC project contained a WBS element, in the IPAC WBS, to provide:

{attribution="[LDM-131](https://ls.st/ldm-131)"}
> This comprises the software needed to "provide automated and human assistance in working with the [Data Management System] and data products" per the WBS. No custom development is anticipated here, the bulk of the task is to choose and configure a COTS Helpdesk system [...]

Traditional helpdesk models are ones where users get support directly from the mission or archive, by either emailing a support address or opening a ticket in a web portal system.
Back-of-the-envelope estimates from anecdotal information would put a (handwaved but likely conservative) active user-to-support request at something like 30-1; if that turned out to be remotely accurate for the Rubin Science Platform users (construction sizing predicted 10,000 users), we would be looking at hundreds of support requests, a level that would quickly turn into a denial-of-service attack on Data Management activities.

SQuaRE identified that the combination of offering a large range of ad-hoc compute capabilities with an anticipated very large user base likely made the traditional helpdesk model unfeasible.
Our approach included identifying ways to facilitate opportunities for peer-to-peer help, similar to the approach of tech companies with massive user bases.
This was the origin of the Discourse-based forum project backing [community.lsst.org](https://community.lsst.org).
This approach was part of an arsenal that enables user self-help (including our documentation engineering efforts) as well as the notebook tutorial infrastructure in the Rubin Science Platform.
We also believe that there is intrinsic merit in creating a helpful user community around LSST data, as it is more likely to support the reach of Rubin science into under-served communities.

During a re-organization of Data Management in 2016, the so-called "Helpdesk" item was transferred to SQuaRE as this item was aligned with SQuaRE's developer and community management tooling activities.

{attribution="[LDM-294](https://ls.st/ldm-294)"}
> **1.02C.10.02.03.03:** Documentation Tooling Documentation standards, documentation linters, software and technical documentation production and publication, developer guide,
user guide, tutorials, document discovery services.
>
> **1.02C.10.02.03.04:** Communication Tooling Community forum, ChatOps.
>
> **1.02C.10.02.03.05:** Bug/Tracking Helpdesk Bug Tracking, Helpdesk, Community Management

As the transition to Rubin Operations got underway, the System Performance department created the Community Science team with the express purpose to support the scientific community's ability to do science with Rubin data.
The Community Science Team adopted Data Management's approach to providing scalable support to the community, for example by adopting the community forum as a platform for enabling user-to-user help (see [RTN-006](https://rtn-006.lsst.io/)) as well as investigating development of new techniques for scalable user support such as AI-delivered knowledge bases.

### Evolution of the Helpdesk deliverable

In light of this approach, one can legitimately ask whether there is still a  need for a Helpdesk deliverable.

Briefly, the answer is yes.
More extensively, both prior experience as well as the experience with Data Preview 0 show that there is still a place for a traditional system for opening support tickets; reasons fall into the following categories:

1. User-specific and private information. An example of this is people with account problems that are specific to them, and that they are either unwilling to discuss in public or it makes no sense to do so (a forum topic of "try resetting your password now" is useless in knowledge base terms).

2. Technical bugs. We expect most observatory-community interactions to be pedagogical in nature ("how do I do this" or "where can I find a history of filter profiles"); nevertheless, sometimes a bug is uncovered that needs attention from the technical teams; or at least needs to be tracked in order to monitor its prevalence (and hence priority). A web forum is an inferior platform for tracking this kind of work - this is why ticketing systems exist.

3. Feature requests. The Rubin technical teams self-evidently do not have the capacity to fulfill every request from a 10K user base. However capturing these requests in a form that allows them to be triaged and in some cases trigger technical work is a key component of evolving the Rubin Science Platform systems in a way that they remain fit-for-purpose. Again, ticketing systems are a better platform for curating these requests than a web forum platform.

The reader who needs convincing of the assertion that ticketing systems are better for these purposes that general purpose forum software is invited to answer a question such as "how many DP0 topics were started on community excluding those filed by Melissa Graham" or "how many unsolved topics were there excluding announcements".
It can be done but it is burdensome.

Note that the latter two do not speak as to who is the "reporter" in the ticketing system, which is a policy issue; for example, it can be the Community Science Team that filters forum traffic in order to open technical bugs.
However we know that "power-users" in particular prefer to open their own tickets, and in fact we have had strong representation at Science Platform User's Committee meeting that reinforce that.
This is an operational process issue and has no bearing on the discussion in this technote, except that due to issue 1 above we do require a ticket system that allows direct user submission and does not scale in pricing per user regardless.


### Data Preview 0

Because the Data Preview 0 program, initiated by Rubin Operations, was not part of the Construction roadmap and due to the relative short preparation time given to the teams to enter full production mode (albeit with a smaller feature set), we took the decision to simply use Github Issues as the issue tracker.
While this was not ideal (for reasons we will cover below), it was a reasonably good match to the Data Preview 0 problem. The first batch of ~ 300 users came at a time we were still using Github as our bootstrap authentication mechanism, which meant that these users had to have Github accounts and had to belong to the Github organisation to which the issue tracking was attached to [rubin-dp0](https://github.com/rubin-dp0/Support/issues).

It's worth noting that despite low ongoing active engagement during the Data Preview (which was based on simulated data of limited interest), there were still 79 issues opened for the technical team.
For reference fewer than 790 users attempted to use the Notebook aspect even once, making for a terrifying 10% technical contact rate (which would scale to 1,000 issues on a 10,000-strong userbase).

But overall, our strategy seemed to be successful.
There were twice as many forum topics initiated by users as issues filed, whereas the pile-up of issues immediately focussed our attention on what was an error-prone sign-up experience; once that was improved, the technical contact rate fell.
Meanwhile the Community Science Team funneled a number of technical issues to the issue tracker from their community events and engagement on the forum.
That's the system working.

### Naming things

While the above analysis reinforces the need for a user-accessible off-the-shelf ticketing system as envisioned in the Construction requirements, the term "Helpdesk" is unhelpful as it carries implications of the kind of support model that we are not staffed to provide, and risks undermining scalable user education efforts such as building a peer support network on the community forum.

In this technote we refer to what was previously encompassed by the Helpdesk WBS element as the **issue tracker** since that is the name of the software applications that underwrite such a service.
It is not intended to pre-judge what the publicly adopted term for this service is, similarly to how "web forum" is the technical term for what is publicly referred to as the "Rubin Community Forum".



