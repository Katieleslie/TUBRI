# TUBRI
Data, lot selection protocol, and analyses conducted using specimens from the Tulane University Biodiversity Research Institute, in support of NSF CAREER award 2141898 entitled, "Reconstructing Parasite Abundance in River Ecosystems Over the Past Half Century"

Welcome to the GitHub repo for the TUBRI fish!

SELECTING FISH FOR DISSECTION

The entire protocol that Chelsea used to select fish for dissection can be found in lot_selection/lot_selection.R.  Here's how it worked:

I decided to focus our data collection on the lower site that Suttkus sampled on the Pearl River, where replication was best before/after 1973 and above/below the mill.  I cut out the proposed sampling on the Alabama River because there were really very few samples above the mill (see Figure 3 in the NSF CAREER proposal).  I would rather do one site really, really well instead of two shallowly.  I think this should be fine, since BACI experiments commonly involve just one site.  I also narrowed to seven fish species that were well-replicated in all four quadrants (before-control, after-control, before-impact, after-impact).

Here is how I generated list of proposed lots (shown in lot_selection/lots_suggested_for_dissection_ROUND1.csv:
- Seven species (Carpiodes velifer, Gambusia affinis, Hybognathus nuchalis, Ictalurus punctatus, Notropis atherinoides, Percina vigil, Pimephales vigilax) were selected from a list of 17 species that are common in the TUBRI collection.  Some species were eliminated because they don't occur in this stretch of the Pearl, others because they weren't well-replicated in all four quadrants (before-control, after-control, before-impact, after-impact).
- time range = 1954-2013
- I decided to focus on just one mill - the one on the lower Pearl River (i.e., the one most intensively sampled by Suttkus; see justification above).
- For each species, I aimed for n = 20 individuals per decade in each of two river stretches (n = 2, above and below the mill).
- For 7 of 9 species, I limited our request to lots with 8 or more individuals, and I ask for only 4 individual fish per lot (regardless of the number of fish in that lot).
- Ictalurus punctatus and Percina vigil are bigger fish, and there tend to be fewer per lot.  For these two species, I limited our request to lots with 4 or more individuals, and I ask for only 2 individual fish per lot.
- total number of individuals requested = 1,178 (across 332 lots)

The above approach needed to be altered based on what was in the collection:
- Because the collection is so expansive, Katie requested the full list of “In Bounds” Lots; all Lots that were within the parameters of the study (the 8 fish species, 1954-2013, Pearl River locations around Mill, and at least 4 or 8 fish in Lot, depending on fish species).  
Using that list she:
- Tried to locate all the lots: if they were not found they were listed as “INVALID”. Lots with fish that were all undeniably too small to dissect were also listed as "INVALID".
- Determined if they were in good enough condition or large enough to dissect at least 2-4 from the Lots without dissecting the largest from each Lot (out of respect for the Lot collection). If so they were considered “VALID”
- Determined “MAYBE” Lots. These should be avoided if there is enough VALID Lots to fulfill our study category targets. The reasons a Lot could have been labelled "MAYBE" are:
    - The Lot had only a 1-3 fish that would be acceptable to dissect, but not the full 2-4 desired from the Lot.
    - The sizes of the fish were likely too small to dissect, but were on the cusp or had some on the cusp of acceptable.
In cases where the VALID Lots are not able to fulfill our study parameters quota, we include all of the MAYBES, not just search for replacements within the VALIDS.

When choosing fish to dissect within the Lots:
- For each species we will determine a Minimum Total Length (TL) of fish we will dissect:
  - I. punctatus: 5cm
  - C. velifer
  - P. vigil
  - N. atherinoides
  - P. vigilax
  - H nuchalis
  - G. affinis
After brainstorming the best way to randomly do this without introducing bias and saving the most time, we decided we would enter the range of the N of the Lot into a Random Number Generator(RNG). However, if all the fish in the lot do not meet the minimum TL, then those will be removed from available fish from the Lot, and the range for the RNG will be reduced accordingly. Additionally, the largest and the smallest of the fish in the Lot will not be dissected and will be removed from the available options. We will do the RNG for each fish we aim to dissect from the Lot. If there are repeats, we will “roll” again. Then, based on the number provided by the RNG, we will count as we remove fish from the jar and dissect the fish we pull on the RNG number.
  - Example: If we are aiming to dissect 2 fish from a Lot with 20 fish, but 6 are under the minimum TL, we will enter 0-13 into the RNG (13 because we are also removing the largest).  We will use the RNG twice to represent the 2 to be chosen for dissection. Say the RNG gives the numbers 5 and 11, we will then start removing fish from the Lot while counting each fish: 1, 2, 3, 4, 5 (this fish will be pulled to dissect, then continue pulling and counting), 6, 7, 8, 9, 10, 11 (this fish will be pulled to dissect). The others pulled will be returned to the jar promptly.
