---
layout: ../../layouts/ProjectLayout.astro
title: "Shelter Stories in the Data"
description: "An analysis of the Austin Animal Center (AAC) intake and outcomes dataset."
github: "https://anjelicam.github.io/aac-shelter-analysis/"
tags: ["Data Analysis", "R"]
---

![chart description](/my-website/images/animal_shelter.jpg)

# Shelter Stories in the Data

## An analysis of the Austin Animal Center (AAC) intake and outcomes dataset

For this project, I used the [Austin Animal Center (AAC) dataset](https://data.austintexas.gov/browse?q=animal&sortBy=relevance&page=1&pageSize=20), which comes from the [City of Austin’s open data portal](https://data.austintexas.gov/). Each row represents a single animal and its outcome: adoption, transfer, euthanasia, or return-to-owner. Alongside that outcome, the dataset records things like species, breed, age at intake, sex, and intake type. Every row represents one shelter animal's visit to the center, a piece of their story.

The dataset spans from mid-2013 through mid-2025 and includes over 130,000 animals. Dogs and cats make up the overwhelming majority thought you’ll also see the occasional bat, racoon or chicken sneaking into the records. The breadth of the data makes it perfect for exploring questions about shelter operations, adoption patterns, and the uncomfortable but important reality of euthanasia. I focused on the ones that get at meaningful shelter outcomes: how long animals stay at the shelter, what factors affect their likelihood of being adopted, and how these patterns vary across species, breeds, and age groups. These are the kinds of questions that matter for shelter policy, for adopters, and ultimately for the animals themselves.

------------------------------------------------------------------------

## Part 1: All Repeat Dogs — First Look at the Numbers

Before diving into detailed patterns, I wanted to get a sense of the big picture: what do dogs who return to the shelter more than once actually look like as a group?

Across all repeat visitors, the number of stays ranged from just two to a jaw-dropping **33** visits (more on him later).

Most dogs didn’t hit such extremes. On average, a repeat visitor came back about 2.3 times, with the bulk clustering around two or three stays. Ages ran the full spectrum, from a few-day-old puppies to seniors pushing 20, though the average was about 3 years old.

Breed patterns stood out quickly. **Pit Bull Mixes** **topped the list**, followed by Labrador Retriever Mixes and other familiar companion breeds. On the sex side, suprinsingly **neutered males** were the single largest group, even though being fixed is supposed to reduce certain return risks (or so you'd think).

These broad strokes already pointed to two paths worth following:

-   Are certain breeds facing bigger barriers to staying in homes?

-   And why are neutered males (typically considered lower-risk) so over represented among repeat visitors?

### 1. How Many Times Do Dogs Return to the Shelter?

For most dogs, repeat visits weren’t a regular habit. Nearly **87% of them were one-time returns**, meaning they came back just once and then (hopefully) settled into a more permanent home. Another **12% came back two or three times**, and fewer than 1% showed up four or five times.

The real outliers were rare. Just 109 dogs cycled through six to nine stays, and only six dogs crossed the double-digit mark.

And then there’s the record-holder: one dog with 33 separate stays. That number is so far off the chart it immediately begged for a closer look. Which is exactly what I did next!

### Snapshot: Lil’ Bit – The Dog With 33 Returns

While most dogs only returned once, a handful became repeat offenders. The most extreme? Lil’ Bit, the Jack Russell with the undisputed record-holder with 33 stays.

Most gaps between visits were short, just a few days or weeks. The median time between stays was about 23.3 days (orange dashed line on the second chart), suggesting a repeating cycle: Lil’ Bit slipped out, ended up at the shelter, and was quickly reclaimed.

But there were exceptions. At one point, he managed nearly a year at home (\~350 days, marked in green) before diving right back into his old routine. His earliest intakes were listed as “stray,” but later ones were usually “Public Assist,” meaning neighbors or community members brought him in.

The chart makes his story clear: each point is both a homecoming and a farewell. His owner always came back for him, but the sheer repetition points to an unsolved problem, whether containment, training, or just one dog’s Houdini-level skills.

Lil’ Bit’s saga is rare, but it sets the stage for a bigger question: are certain breeds more likely to become repeat visitors?

### 2. Most Common Dog Breeds Returning to the Shelter

When it comes to repeat returns, one group towers above the rest: **Pit Bull Mixes**. Nearly 4,000 of these dogs came back to the Austin Animal Center after adoption or placement, that's almost double the number of the next runner-up, Labrador Retriever Mixes.

After that, the numbers taper off but are still notable. Chihuahua Short-Hair Mixes, German Shepherd Mixes, and purebred Pit Bulls round out the next tier, with each accounting for thousands of returns. The rest of the top ten, breeds like Australian Cattle Dog Mixes, Boxers, and Staffordshire Mixes, still represent hundreds of cases each.

This doesn't seem to be just about breed popularity in Austin. The pattern could reflect deeper challenges:

-   Housing and insurance restrictions that limit where certain breeds can live.

-   Behavioral traits that require more training than many adopters anticipate.

-   Mismatches between dogs and households that only become obvious after the honeymoon period ends.

The data doesn’t tell us the “why” outright, but it does point us toward where to look. If the goal is to cut down repeat returns, these breeds are the logical starting point for targeted outreach, training support, and adoption counseling.

Of course, breed is just one part of the story. Another angle worth exploring is **sex,** not just male versus female, but whether the dogs were intact or already fixed.

### 3. Sex and Spay/Neuter Status of Repeat-Return Dogs

When we imagine dogs that keep ending up back at the shelter, the stereotype is usually of intact males roaming the neighborhood looking for a mate. But the numbers tell a different story.

While yes, males do make up the majority of repeat returns, 14,413 (57.5%) compared to 10,637 (42.5%) females, most of them weren’t intact. In fact, nearly two-thirds of the males (8,668 dogs, or 60.1%) were already neutered at intake. Among females, the pattern looks the same: 62% were spayed.

That’s important because it pushes back against a long-standing assumption in sheltering: that mating behavior is the main driver of repeat returns. The data suggests otherwise. Issues like behavior, housing restrictions, or sudden changes in an owner’s life are more likely culprits.

In other words, fixing the animal doesn’t necessarily address the problem.

So far, we’ve looked at who these repeat dogs are. Next, I turned to when they tend to return, to see if any seasonal or historical patterns stood out.

### 4. Sex Distribution Within the Top 10 Repeat-Return Breeds

In the last section, we saw that most repeat-return dogs were already spayed or neutered, which challenges the idea that intact males are driving the pattern. So the next question is: within the breeds most likely to come back, does one sex tip the scales?

In this chart, the dashed vertical line marks a 50/50 split. Bars leaning further to one side show a stronger skew. For most of the top-return breeds, the skew leans male. Labrador Retrievers, German Shepherds (both purebred and mixes), Pit Bulls, and Australian Cattle Dog mixes all had more male than female returns, with Labs showing the sharpest imbalance.

The one outlier was Staffordshire Mixes, where females actually made up the majority of returns. That tells us sex does play some role, but it’s not a one-size-fits-all story. It’s probably shaped by a mix of breed behavior patterns, adoption preferences, and the general population of dogs coming through the shelter.

With the “who” questions in mind, I then turned to the “when”, looking at whether certain seasons or historical shifts shaped the timing of these returns.

### 5. Monthly Repeat Dog Intakes at Austin Animal Center

This heatmap tracks how many repeat-intake dogs came into the Austin Animal Center each month from 2014 through 2024. (I omitted both 2013 and 2025 because of incomplete data).

How to read this chart:

-   Each row is a year; each column is a month.

-   Darker shades mean fewer repeat intakes; lighter, hotter shades mean more.

-   Look for horizontal bands (seasonal patterns) or sudden shifts (events or disruptions).

**What the data shows\
**Before 2020, strong seasonal cycles appeared, with repeat returns peaking in late spring and summer (April–July). These surges likely align with "relocation season", when leases turn over, schools let out, and families are more likely to move. Moves often bring housing restrictions or disruptions that can force pet returns.

In 2020, the pattern broke sharply: repeat intakes dropped across nearly every month. This coincides with the COVID-19 pandemic, when shutdowns, higher adoption rates, and expanded fostering programs kept many dogs out of the shelter.

By 2021–2023, intakes began to rebound, suggesting some “pandemic pets” were eventually returned. Even so, the most recent years (2023–2024) remain below the pre-pandemic highs of 2017–2019, possibly reflecting improved adoption screening, owner support, or changes in shelter policies.

This monthly view highlighted two things clearly: consistent pre-pandemic peaks and a dramatic COVID-era dip. But one finding kept resurfacing in earlier analyses: neutered males consistently make up the largest share of repeat intakes. That made them worth a closer look.



## Part 2: Neutered Males

In Part 1, we saw that male dogs make up a bigger share of repeat returns than females, and most of them were already neutered. That alone challenges the stereotype that intact males are the main culprits behind repeat visits. To dig deeper, I looked at how these neutered males were coming back to the shelter.

### 1. Why Neutered Males Return Multiple Times

**Owner-driven returns** stood out as the single biggest factor. Almost half (47.4%) of repeat intakes for neutered males were **owner surrenders**, cases where the owner brought the dog back themselves. The data doesn’t give exact reasons, but it likely includes things like housing restrictions, financial struggles, changes in family circumstances, or behavior issues that proved too much to handle.

**Stray intakes** made up another 39.6% of cases, where neutered males were picked up roaming and returned by a member of the public. A smaller share (12.3%) came in through “public assist” cases, where animal control or another city agency had to step in. The last 0.8% fell into “other” categories too uncommon to analyze.

Taken together, the numbers show that neutered males aren’t just escape artists, they’re often repeat visitors because of their owners’ circumstances or decisions. Without detailed “intake subtypes” we can’t know the exact why, but the categories point more toward human factors than the dogs themselves.

### 2. Where Neutered Male Dogs End Up After Returning to the Shelter

After flagging neutered males as the largest group of repeat-intake dogs, I looked at what happened each time they left the shelter.

The most common outcome was adoption, making up nearly half of all cases (46.8% or 4,358 dogs). Another 31.8% (2,962 dogs) were reclaimed by their original owners. Transfers to partner rescues or organizations accounted for 12.1% (1,126 dogs).

Most dogs left the shelter alive, but not every story ended that way:

-   Euthanasia: 1.7% (157 dogs), usually for behavioral or medical reasons.

-   No Outcome Recorded: 0.5% (49 dogs).

-   Died in Care: 0.1% (11 dogs).

-   Died (Disposal): 0.04% (4 dogs).

-   Missing: \<0.01% (1 dog).

These numbers tell us the big picture, but outcomes often depend on how a dog came back, whether as an owner surrender, a stray, or through another path. So next, I broke outcomes down by intake type to see if the story changes depending on how the dog re-entered the system.

### 3. What’s behind the negative outcomes?

Breaking outcomes into subtypes gives us a sharper picture.

-   **Transfers:** Nearly all went to partner rescues (95.6%, or 1,076 dogs), with a smaller share to out-of-state partners (4.4%, or 50 dogs).

-   **Foster:** 589 dogs were placed in foster homes, often a stepping stone toward adoption.

-   **Euthanasia:** The majority were for behavioral or aggression-related reasons (103 cases, 65.6%). Another 32 cases (20.4%) were due to medical issues or suffering.

This means nearly 9 in 10 neutered male repeat-intake dogs eventually leave the shelter alive, most through adoption or reunification. But the small fraction facing life-ending outcomes points to clear pressure points: behavior support, medical care, and adoption matching. Strengthening these areas could help reduce the cycle of returns and improve long-term outcomes.



### 4. Outcomes by Intake Reason: Neutered Males

This chart compares what happened to neutered male dogs after returning to the shelter, split into two groups: owner surrenders and non–owner surrenders (strays or public assist).

-   **Owner Surrenders:** Most were rehomed (74.3% were adopted). Transfers made up 18.7%, while just 4.0% were reunited with their original owner. Euthanasia occurred in 2.0%.

-   **Non–Owner Surrenders:** The majority (61.4%) were reclaimed by their families. Adoption followed at 28.6%, then transfers at 7.8%. Euthanasia occurred in 1.6%.

Owner-surrendered dogs tend to move on through adoption, while non–owner surrenders are most often reunited with their original families. In both groups, euthanasia remains rare but slightly more frequent among owner surrenders.


### 5. Most Common Breeds in Repeat Neutered Male Dog Intakes

After looking at outcomes, the next question is which breeds dominate this group of repeat-intake neutered males.

Again, **Pit Bull Mixes** stand out by a wide margin, with more than 300 repeat intakes, nearly double the number of Labrador Retriever Mixes, the next most common breed. Behind them are Chihuahua Shorthair Mixes and German Shepherd Mixes, though their numbers are far smaller compared to Pit Bull Mixes.

This skew matters because when one or two breeds dominate, their outcomes shape the overall picture. If Pit Bulls are returned more often, then their adoption, transfer, or euthanasia rates weigh heavily on the shelter’s statistics. It also raises the possibility that breed-specific barriers, like housing restrictions, behavioral expectations, or adopter mismatches, are at play.

This means that the over representation of a few breeds means that targeted adoption counseling, breed-specific support, or community education could make a measurable impact on reducing repeat returns.

# Conclusion & Implications

This analysis of repeat dog intakes at the Austin Animal Center shows that while most dogs return only once, a smaller but important subset (especially neutered males) cycle back multiple times. Breeds such as Pit Bull Mixes, Labrador Retriever Mixes, and Chihuahua Shorthair Mixes are disproportionately represented, which means their outcomes weigh heavily on the shelter’s overall trends. Intake reason also matters: owner surrenders are most often rehomed through adoption, while non–owner surrenders are more often reunited with their families. Seasonal peaks before 2020, the sharp pandemic drop, and slower rebounds afterward suggest that community behavior and shelter operations strongly shape return patterns.

## Critical Reflection

This project really challenged some of the usual assumptions about why dogs keep coming back to shelters. I honestly expected intact males to dominate the repeat-intake group, but the data showed something else entirely: neutered males actually made up the *largest* share. That shifted my perspective and made it clear that returns are often less about the dog’s biology and more about human factors like housing restrictions, financial struggles, or adopters feeling overwhelmed.

Linking intakes and outcomes at the individual dog level was another eye-opener. Instead of just seeing totals, I could actually follow dogs through multiple visits, which revealed patterns I wouldn’t have noticed otherwise. The biggest one was the split between owner surrenders and non-owner surrenders (owners bringing dogs back themselves vs. dogs being found as strays). That difference shaped outcomes in big ways.

Of course, the dataset had limits. The “owner surrender” category doesn’t tell us whether someone gave up their dog because of money, housing, or behavior. “Adoption” just tells us the dog left with someone new, not whether the placement stuck. Bigger context, like breed restrictions in housing or local eviction rates, is also missing, even though those things probably play a huge role. And because this is just one city shelter, the results can’t be applied to every type of shelter, especially limited-intake ones.

Working through these gaps made me think more about ethics in shelter data. It’s easy to point to breed patterns, but that can reinforce stereotypes if you don’t acknowledge the bigger picture of adopter bias, housing discrimination, and systemic barriers. It also matters that the dataset was de-identified, it's less detail to work with but a necessary trade off to protect people’s privacy.

In the end, this project gave me stronger technical skills and a better sense of how messy real-world data connects to animal welfare. It also left me with new questions: how age affects repeat returns, how community-level issues like poverty and housing impact intakes, and what kinds of support actually help keep dogs in homes. Those are the kinds of things I’d want to dig into next, since they’d make future research more useful not just for shelters, but for adopters and especially for the sweet pups who end up back in the system.

------------------------------------------------------------------------

# References

ASPCA. (2024). Pet statistics. ASPCA. <https://www.aspca.org/helping-shelters-people-pets/us-animal-shelter-statistics>

City of Austin, Texas. (2025). Austin Animal Center intake and outcome data (2013–2025) \[Data set\]. City of Austin Open Data Portal. <https://data.austintexas.gov>

Grolemund, G., & Wickham, H. (2017). R for data science: Import, tidy, transform, visualize, and model data. O’Reilly Media.

Hawes, S. M., Kerrigan, J. M., & Morris, K. N. (2020). Factors informing outcomes for older cats and dogs in animal shelters. Animals, 10(5), 746. <https://doi.org/10.3390/ani10050746>

Long, J. D. (2019). R cookbook: Proven recipes for data analysis, statistics, and graphics (2nd ed.). O’Reilly Media.

Miller, J. E. (2005). The Chicago guide to writing about multivariate analysis. University of Chicago Press.

Patronek, G. J., Glickman, L. T., Beck, A. M., McCabe, G. P., & Ecker, C. (1996). Risk factors for relinquishment of dogs to an animal shelter. Journal of the American Veterinary Medical Association, 209(3), 572–581. <https://pubmed.ncbi.nlm.nih.gov/8755975/>

R Core Team. (2025). R: A language and environment for statistical computing. R Foundation for Statistical Computing. <https://www.R-project.org>
