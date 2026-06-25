# Lignin-Alginate Hydrogel Copper Sensor

### What This Project Is
This is a hydrogel bead sensor that detects copper contamination in water by changing color to orangish-yellow when copper is present. The sensor doesn't need any external equipment for point of use, the goal is to drop the bead into water, wait a couple minutes and read the color change. A smartphone camera app can be built which allows reading of specific copper concentrations in water.

The bead is made from 4 components: sodium alginate (a seaweed-derived polymer), kraft lignin (a wood pulp waste product), bathocuporine disulfonate (BCS) which is a highly selective copper indicatior, and borax. The sensing mechanism works through lignin's ability to reduce Cu2+ to Cu+ at alkaline pH, which BCS then selectively captures to produce the visible color signal. This system replaces the need to use external reducing agents such as ascorbic acid, hydroxylamine, or any other external reducing agent. 

### Why This Matters
The EPA copper action level for drinking water is 1.3 mg/L (13000 ppb) but water systems continuously exceed this threshold. This poses a dangerous threat for people who are drinking from these sources. Existing copper detection methods require advanced labratory equipment suchas ICP-MS or Atomic Absorption Spectrosopy (AAS) or comercial test kits with multiple reagent steps. Neither is practical for rapid field screenign in low-resource settings, community water monitoring, or in educational contexts. This sensor addresses this gap with materials that are affordable and can be prepared easily with basic equipment.

### Initial Concept

The project previously included Chitosan since it would provide structural reinforcement of the gel through polyelectrolyte complexation with alginate, and electrostatic retention of BCS through interaction between chitosan's catioinc amine groups and BCS's anionic sulfonate groups. 

The first problem was that Chitosan and alginate are a polycation and polyanion so when they aare combined they spontaneously form a polyelectrolyte complexation. The precursor turned into a semi-solid paste which would instantly pop as the alginate bubbles would pop instantly. Initially I thought this was due to the calcium chloride (the crosslinker) concentration which was so low that when the precursor formulation was deposited by the syringe it still remained a paste.

<img width="1034" height="728" alt="image" src="https://github.com/user-attachments/assets/10ec8748-547c-4419-b6a8-ff515808fab9" />

I attempted to get the crosslinking to work faster by colling the solutions so the reaction would occur faster once combined, to add chitosan more slowly, to change the addition order but it all produced the same result

<img width="1034" height="728" alt="image" src="https://github.com/user-attachments/assets/8f807d0d-f112-4ff0-8212-0bdd9118b014" />

After reading more papers I found that chitosan could not be used in this sensor at all, regardless of the gel formation issue! Chitosan's amine groups chelate Cu2+ with a log K of 8-10, with equilibration times around ten minutes at pH 5-7. The sensor's entire mechanism depends on Cu2+ reaching the lignin inside the gel. Chitosan placed anywhere in the copper flow path before the lignin woudl intercept the copper and produce no signal. This is why I removed Chitosan from the protocol. 

### Gel Formulation Failures
Without chitosan, the gel formulation problem could be narroed to just the crosslinker. I had to use several different approaches which slowly built upon each other's success

#### Attempt 1: External CaCl2 flooding of petri dish, 0.1 M
The Alginate-lignin precursor was poured into a 90mm petri dish at about 3-5mm depth and flooded with 0.1M CaCl2 from above. The result was a dense gel skin forming at the top surface within seconds, blocking Ca2+ from diffusing to the bottom. I left these gels overnight one outside and one in the 4 degree celsius fridge but nothing changed. The problem was that the gel skin formed faster than Ca2+ could diffuse through it.

<img width="998" height="1330" alt="image" src="https://github.com/user-attachments/assets/06411fc5-cafb-45b1-afcd-a59cb0d25680" />

#### Attempt 2: CaSO4 internal gelation
[A Nature Communicatons paper](https://www.nature.com/articles/s41467-022-30691-z) described a method of using CaSO4 slurry mixed direcly into alginate for internal, uniform gelation before being compressed for MPa-range stiffness. CaSO4 was calculated at 15 wt% relative to algiante mass and mixed as a 11% w/v slurry. 

When I used this method the CaSO4 released Ca2+ the moment it contacted the alginate solution. Gelation began within thirty to sixty seconds of addition, which was faster than the precursor could be poured creating lumps and overall a non-uniform gel. I tried multiple attempts with pre-chilled solutions, faster pouring and increasing the stir speed but it all had the same result. I was considering using Calcium Carbonate but I didn't have any readily available. I decided that the best move was to stick with Calcium Chloride. 

#### Attempt 3: Sandwich Flooding
I poured CaCl2 into the petri dish first then the alginate-lignin precursor on top, then add more CaCl2 on top. The precursor is now sandwiched with Ca2+ on both sides, which should give uniform two-sided crosslinking. The results here were better but the preursor layer was displaced unevenly and the pieces were irregular.

#### Attempt 4: Syringe drip into CaCl2 bath, 0.1 M
I settled upon the bead concept by dropping the precursor mixture with Sodium Alginate (I didn't use lignin since these were just tests to see if it works) from a syringe into the CaCl2 solution after seeing [this video](https://youtu.be/x2SKhcUB6Zo?si=LrSrtLuyMJKPu-yF). At 0.1M, the beads formed but were soft but could be squished with a bit of effort and showed some seeping over time.

<img width="998" height="1332" alt="image" src="https://github.com/user-attachments/assets/fb9dfc45-976c-421c-b706-7054db490ec2" />

Synergsis was driving fluid loss because the bath ionic strength was much lower than the gel interior, creating an osmotic gradient that pulled water out.

#### Attempt 5: Syringe drip into 1M CaCl2
This worked! At 1M CaCl2, the droplet contacted Ca2+ from all sides simultaneously the moment it hits the bath, forming a gel skin instantaneously and crosslinking inward uniformly. The beads are approximately 1mmm in diameter, hold their shape under handling, and survived a full-flow tap water without breaking. This proved that the gels were strong and required a bit of force to pop. 

### The BCS Sensing Mechanism Problem
With working gel beads in hand, I decided the next task was incorporating BCS and confirming the sensing response.

#### Attempt 1: BCS in the precursor
BCS was added to the alginate-lignin mixture before extrusion. The beads formed normally. When placed in copper sulfate solution the beads turned blue (Cu2+ binding to alginate carboxylates) but showed no orange-yellow color. The reason was since BCS has two anionic sulfonate groups and alginate is also anionic. Since like charges repel, during the 15 to 20 minute in a 1 M CaCl2 bath, BCS was completely expelled from the gel by electrostatic repulsion before any copper testing could occur. By the time the bead entered copper solution it contained no BCS.

#### Attempt 2: Lignin outside the gel, BCS inside
Beads were made with BCS and alginate, no lignin. The surrounding test solution contained lignin and copper sulfate but there was no color change. The test confirmed that copper was diffusing into the gel as the beads turned blue. Lignin in alkaline solution reduces Cu2+ to Cu+, but Cu+ is thermodynamcally unstable in aqueous solution and disproportionates back to Cu2+ and Cu0 in seconds. The Cu+ does not survive long enough to actually diffuse into the alginate gel wall and reach the BCS that is mainly inside.

#### Attempt 3: Free solution tests to diagnose the problem
A series of diagnostic free solution tests were run to identify exactly the problem
- BCS Stock in DI water gave a faint yellow color which is expected confirming that the BCS was not degraded
- BCS was added to copper sulafte solution and there was a yellow color chainge further confirming that the BCS works
<img width="1024" height="768" alt="6A53CA1F-EA3F-4073-8781-D7CED7D2F0F5_1_105_c" src="https://github.com/user-attachments/assets/95a94e26-b812-475e-ac1f-144bce1aba3b" />
- Lignin added to a pure copper powder solution which broke down the Cu2+ which repelled the water and began to allow the water to mix confirming that the Lignin was working

I found papers which told that the reaction between a basic solution of lignin and copper sulfate leads to formation of CU2O where wcuprite nanocrystals are embedded in teh lignin framework. At neutral pH, lignin phenol groups are protonated (pKa 9 to 10) and cannot donate electrons. At pH 9.5 a significant fraction are deprotonated as phenolates, which are the active electron donors for Cu2+ reduction.

### Solving the Retention and pH Problem
Two problems remained, how to keep BCS inside the gel, and how to maintain alkaline pH inside ht ebead when it contracts neutral test water.

#### BCS retention: post-loading
instead of adding BCS to the precursor whre it gets expelled during Ca2+ crosslinking, BCS is loadde int the finished bead from outside agter gelation. Cured beads are soaked in 0.3mM BCS solution at pH 9.0 to 9.5 for 2-4 hours. BCS diffused in from the surrounding solution down the concentration gradient. because there is no competing high-ionic-strength bath drawing it back out, it distributes through teh gel and stays. The first time this was tried with immediate testing, a color change appeared. The inconsistency in early tests was because sometimes the bead was tested quickly enough that CBS was still inside, and sometimes it was tested after BCS had time to leach out.

#### Internal pH control: Borax
H+ diffuses through a 1mM gel approximately twenty times faster than Cu2+. If the bead is at pH 9.5 but the test water is at pH 7, the interior pH collapses to 7 within seconds of immersion, long before Cu2+ enters the bead. The lignin phenolates are immediately re-protonated and inactive. The fix is to embed a pH buffer inside the bead. Borax is dissolved in the precursor and titrated at pH 9.5 with NaOH whcih is the range to engage lignin phenolate activity.  This approach allows to test water pH to reamin unadjusted so the BCS won't leach.

### Final working system 
The complete validated protocol:

1. Dissolve 2.000g sodium alginate in 100mL deionized water at 50°C with 400rpm stirring for two hours minimum
2. Add 0.093g boric acid per 30mL precursor batch and stir to dissolve
3. Add 0.2mL of 1% w/v lignin dispersion (lignin pre-dissolved in 0.1M NaOH) per 30mL precursor
4. Titrate with 0.1M NaOH to pH 9.5 to 10.0
5. Extrude into 1M CaCl₂ bath by syringe
6. Cure 15 to 20 minutes
7. Brief rinse with deionized water
8. Soak in 0.3mM BCS solution at pH 9.0 to 9.5 for two to four hours in subdued lighting
9. Beads are ready for copper sensing

### How a stranger would experience this project
A person would take a small vial of finished beads, drop about 3-5 into a water sample, wait 15 minutes, and observe whether the beads have turned orange-yellow. A color card printed on paper showing the gradient from blank (no color change) through action-level concentrations provides a field-usable reference for interpretation. A smartphone application could photograph the beads against white paper and color analysis using an RGB extraction app provides a semi-quantitative reading corelated to a calibration curve. 

### Materials and where to get them
All materials were sourced from SoundBio Lab's community stockroom or are commercially available.

- Sodium alginate: Sigma-Aldrich or equivalent, food-grade acceptable
- Kraft lignin: Sigma-Aldrich, technical grade
- Bathocuproine disulfonate (BCS): Sigma-Aldrich, requires careful light-protected handling
- Borax: standard lab reagent, widely available
- Calcium chloride dihydrate: standard lab reagent
- Sodium hydroxide: standard lab reagent
- Copper sulfate pentahydrate: standard lab reagent, used to make test solutions

### What was learned
The assumption assumption that lignin would reduce Cu2+ to Cu+ at neutral pH without any additional conditions was false! I needed to add borax to maintain a basic solution, not a neutral solution. the phenol group of lignin are not active electron donors until they are deprotonated, which requires a pH 9 or above given their pKa of 9 to 10.

The electrostatic repulsion between BCS and alginate was also not anticipated. Both are anionic. Alginate actively repels BCS during gelation in a high ionic-strength bath. The post-loading approaching was discovered through troubleshooting, not from the literature, and turns out to be the cleaner method anyway since it allwos the gel to fully cure before any sensing component is introduced.
