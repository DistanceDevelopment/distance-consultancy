Project Governance -- dissection
================================

This is a chopped-up and prioritised version of the document prepared by Mike Jackson. Titles are same as in original Governance doc where possible for cross-referencing.

The below table was created by Dave Miller and Eric Rexstad to attempt to get a handle on what we need to do.

| Time/importance                                              | Short (≤1 day)                                                               | Medium (≤1 month)                                                                           | Long (multiple months)                                                       |
|--------------------------------------------------------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| **Less important ("it,would be nice if...")**                    | *Add* the citation request to release-specific download pages                  | Cross-reference e-mails from downloaders with e-mails to the forum | Be specific when mentioning previous versions in documentation               |
|                                                              | Make the citation request a requirement         | Ask other projects whether some form of mutual promotion can be done                        |                                                                              |
| **Moderate importance (we look silly)**                        | Point workshop bibliography page to new bibliography (Rhona/Steve,Smart)     | Clarify licensing of Distance extras                                                        | Write a backwards compatibility policy                                       |
|                                                              | Adopt an issue tracker                                                       | Define a support process & policy                                                           | Write a policy about compatibility of Distance extras with Distance releases |
|                                                              |                                                                              |                                                                                             | Automate upgrade support                                                     |
| **Highly important (things will explode/what if a bus hits...)** | Ensure more,than one team member can access distance@mcs.st-and.ac.uk (Phil) |                                                                                             |                                                                              |


# Further dissection

There is a third axis which is "how likely are we do to this?". I've tried to group related issues here.

## Highly likely

### Define a support process & policy

I propose the following policy:

*We officially support Distance back to version `DX` and R packages back to those released with Distance version `DX`. If you find a bug in Distance or related R packages (i.e. the program crashes, an error message appears or output is clearly incorrect) this chould be submitted to `BUG_TRACKER` (details for submitting a bug are available at `BUG_TRACKER_HOWTO`). If you have a problem getting your data into Distance, you don't understand an output or are unclear over whether what you're experiencing is a bug or not, please post details to the Distance sampling mailing list at `https://groups.google.com/forum/#!forum/distance-sampling`. Please don't contact Distance developers directly with bugs.*

where `DX` is the oldest version of Distance we want to support (5? 6?), `BUG_TRACKER` is a single master bug tracker for everything, `BUG_TRACKER_HOWTO` is a friendly document telling you how to use the system. Related to this is Mike's [suggested "Get in touch" page](https://github.com/softwaresaved/distance-consultancy/blob/master/GetInTouch.md) and ["how to get help" page](https://github.com/softwaresaved/distance-consultancy/blob/master/HelpAndSupport.md). This also (in part) tackles the "Write a backwards compatibility policy" issue.

An adjacent issue to this is "Adopt an issue tracker". I think we should do as Mike suggests in [the governance document section](https://github.com/softwaresaved/distance-consultancy/blob/master/Governance.md#adopt-an-issue-tracker) and migrate to github ("There have been issues with users being reluctant to use Bugzilla - GitHub issue trackers have a far less intimidating user interface") -- though I do disagree with Mike on having two issue trackers (one for Distance and one for the Fortran code) since this difference is invisible to the user, we should instead just have one issue tracker for Distance and re-assign to the R project issue trackers if necessary (referencing between issues in the github tracker is easy).

I'm willing to sit and work out how to do the migration from Bugzilla to GitHub Issues.



### Revise "Distance Extras"

Two issues:

  * Write a policy about compatibility of Distance extras with Distance releases
  * Clarify licensing of Distance extras

Eric has volunteered to look through the current extras page and prune it. Some items are only really relevant to older versions of Distance. We can then have an archive page of stuff for old releases. Licensing of extras items is hard, some will be clear (we wrote them, or they are owned by e.g. Microsoft) but others are big question marks.


### Be specific when mentioning previous versions in documentation

This can be corrected as we go through writing Distance 7 docs, but as pointed out [elsewhere by Mike](https://github.com/softwaresaved/distance-consultancy/blob/master/DeveloperExperienceReview.md#use-wikis-or-revision-control) we should move towards some kind of version control in the documentation. Additionally, we need to work out where the canonical version of the documentation is -- I would strongly argue that "on Len's hard drive" is not an option.


## Somewhat likely

  * *Add* the citation request to release-specific download pages
    - We can add this (or a link to the citation) to the download pages, still useful to have somewhere central too though.
  * Ask other projects whether some form of mutual promotion can be done
    - Happy to ask Jason & MGET folks if this is possible. Not sure about other groups.

## Unlikely

  * Automate upgrade support
    - dependent on what's next for Distance (post 7)
  * Cross-reference e-mails from downloaders with e-mails to the forum
    - likely to become a candidate summer student/MSc project
  * Make the citation request a requirement
    - beyond our control, can't really force people to cite. What are RAE/REF etc implications?

## Started work on

  * Ensure more,than one team member can access `distance@mcs.st-and.ac.uk`
    - need to find out what's going on from Phil (`@mcs` issues).
  * Point workshop bibliography page to new bibliography
    - check with Mike where this error is, ask Rhona/Steve Smart to edit page



