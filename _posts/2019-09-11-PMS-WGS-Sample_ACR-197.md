---
layout: post
title: Library Prep of Whole Genome Sample ACR_197 
tags: [ Shearing, Sonication, DNA, Library Prep ]
---
### Library Prep using [Zymo Pico Methyl Seq Kit](https://www.zymoresearch.com/products/pico-methyl-seq-library-prep-kit) of [ACR_197](https://echille.github.io/E.-Chille-Open-Lab-Notebook/Acropora-Larvae-DNA-RNA-Extraction-Batch-1/) which will be a Whole Genome sample to be sequenced with the other 9 ACR_sperm samples from the project FACE_PUF

ACR_197 was previous labeled as "too low" for Qubit values but looking at the gel, the banding pattern indicates that there should be plenty of DNA present for DNA sequencing.

Plan: Going to shear the DNA to the 650-500bp range using the [Q800R3 Sonicator](https://www.sonicator.com/collections/sonicators/products/q800r-sonicator) via [DNA Shearing Protocol](https://meschedl.github.io/MESPutnam_Open_Lab_Notebook/Sonication-Test/) before running ACR_197 through the Pico Methyl Seq Kit

First thing I did was Qubit the DNA in the remaining sample for ACR_197 using the High Sensitivity Assay

3 samples (two standards and ACR_197) ;
		Buffer Required: 199 * 3.2 = 636.8uL (0.2 is for pipette error)
		HS Dye: 1 * 3.2 = 3.2uL
				Working solution was vortexed well and spun down to get rid of any bubbles before being pipetted out for each tube (190uL for standards and 199uL for ACR_197)

**Summary Table of Qubit Results**

|Sample Id|Concentration 1| Concentration 2| Avg Concentration (ng/uL)|
|----|-----|-----|-----|
|Standard 1|NA|NA|49.80(ng/mL)|
|Standard 2|NA|NA|26166.61(ng/mL)|
|ACR_197|4.06|4.02|4.04|

For the [shearing protocol](https://meschedl.github.io/MESPutnam_Open_Lab_Notebook/Sonication-Test/) input requires 1ug or 1000ng of DNA from the sample but it is limited to 50uL for the sonicator tube

	So: (1000ng) / (4.04ng/uL) = 247.52 uL required to get 1000ng or 1ug of input DNA
	
*Since the volume is restricted to 50uL I just used 50uL of sample DNA (still about 50uL left just in case need to redo)

|Sample Id|DNA Input Vol (uL)| Water Input (uL)| Shear Time|
|----|-----|-----|-----|
|ACR_197|50|0|1:00|

Sheared for 1 minute (4 cycles of 15s on 15s of -> technically 2 minutes but 1 minute of actual shearing occuring) at 25% Amplification


**D5000 TapeStation**

![ACR_197]({{ site.baseurl}}/images/20190911_ACR_197_DNA_Shearing.png "ACR_197")

See [Full Results](https://github.com/dconetta/DAC_Putnam_Lab_Notebook/blob/master/tapestation.pdfs/2019-09-11%20-%20ACR_197_DNA_Shearing.pdf)

After the shearing, I re-Qubited (HS Assay) the DNA to know exactly how much I will have/need to put into the Pico Methyl Seq Kit

|Sample Id|Concentration 1| Concentration 2| Avg Concentration (ng/uL)|
|----|-----|-----|-----|
|Standard 1|NA|NA|57.56(ng/mL)|
|Standard 2|NA|NA|26415.11(ng/mL)|
|ACR_197|4.00|3.86|3.88|

1ng needed for input of the Pico Methyl Seq Kit
	(1ng)/(3.88ng/uL) = 0.258uL
	
*Since this is a very small volume and prone to errors in pipetting, did a 1:10 dilution. Added 1uL of sheared DNA to 9uL of ULtra Pure Water ;

2.58uL of diluted DNA was inputed at the start of this Kit 

|Sample|DNA Conc (ng/uL)|Volume of Input DNA (uL)|Volume of Water (uL)|
|----|----|----|----|
|ACR_197|3.88|2.58|17.42|

***Section 1: BS Conversion***
**Conversion Reaction**

- 20µl of each tube was taken and pipetted into new PCR tubes, one for each sample  
- 130µl of Lightning Conversion Reagent was added to each tube, vortexed, then spun down
- The 5 tubes were put into the thermocycler bisulfite conversion program (under mes user), which is 98 degrees C for 8 minutes, then 54 degrees C for 60 minutes, then 4 degree C hold

**Conversion Cleanup**

- Added 600µl of M-Binding buffer (lightning kit) to the provided Zymo-Spin IC Columns (4 of them, one per sample)
- Added the bisulfite treated DNA (150µl) to its respective column and inverted to mix
- Centrifuged at 12,000 rcf for 30 seconds and discarded flowthrough
- Added 100µl M-wash buffer to each column and centrifuged at 12,000 rcf for 30 seconds
- Discarded flowthrough
- Added 200µl L-Desulfonation buffer to each column and let them sit at room temp for 15 minutes
- Began warming elution buffer to 56 degrees C
- Centrifuged for 30 seconds at 12,000 rcf and discarded flowthrough
- Added 200µl M-wash buffer, centrifuged for 30 seconds at 12,000 rcf and discarded flowthrough
- Repeated above wash step one time
- Transferred columns to 1.5mL tubes
- Added 8µl warmed elution buffer to the columns and let them sit for 1 minute
- Centrifuged for 30 seconds at 12,000 rcf

***Section 2: Amplification with PrepAMP Primers***
- Made Priming master mix on ice:
  - 2µl 5X PrepAmp buffer *No mastermixes were created for any of these sections since only had the one sample
  - 1µl PrepAmp Primers (40µM) 
- Made new PCR tubes with 3µl of PrepAmp MM and 7µl of bisulfite treated DNA (100ng, 10ng, 1ng, 100pg, 10pg)
- Kept those on ice
- Made PrepAmp Mix on ice:
  - 1µl 5X PrepAmp buffer 
  - 3.75µl PrepAmp PreMix
  - 0.3µl PrepAmp polymerase 
- Set thermocylcer program with lid temp restricted to 25 degrees C and place samples inside and run:
  - 98 for 2 minutes
  - 8 degrees for 1 minute
  - 8 degree hold
  - **During hold vortex, spin tubes down, add 5.05µl PrepAmp Mix to each tube, vortex, spin down, and place back in thermocycler**
  - 8 degrees for 4 minutes
  - 16 degrees for 1 minute with 3% ramp rate
  - 22 degrees for 1 minute with 3% ramp rate
  - 28 degrees for 1 minute with 3% ramp rate
  - 36 degrees for 1 minute with 3% ramp rate
  - 36.5 degrees for 1 minute with 3% ramp rate
  - 37 degrees for 8 minutes
  - repeat back from the first step one time through again
  - **During hold, vortex, spin tubes down, add 0.3µl PrepAmp Polymerase to each tube, vortex, spin down, and place back into thermocycler**
  
***Section 3: DNA Clean and Concentrator Columns (DCC)***
- Made a 1.5mL tube for each sample, added 7:1 ratio DNA binding buffer, so 250.81µl (Should have been 107.45uL) of DNA binding buffer and 15.35uL of Product
- Put elution buffer in thermomixer 56 degrees
- Added DNA sample (15.35µl) to the appropriate 1.5mL tube
- Vortexed, spun down, and added to the column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Added 200µl M-wash buffer to each column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Added 200µl M-wash buffer to each column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Transferred columns to 1.5mL tubes
- Added 12µl warmed elution buffer to each column directly
- Incubated 1 minute
- Centrifuged 12,000 rcf 30 seconds

***Section 4: Second Amplification (Adapater Addition)***
- Made 1st Amp master mix:
 - 12.5µl 2X Library Amp Mix 
 - 1µl Library Amp Primer(10µM) 
- Added 13.5µl MM to new PCR tubes
- Added 11.5µl of cleaned and concentrated DNA sample to the appropriate new PCR tube
- Vortexed, spun down, and placed in thermocycler programs specific to how many cycles each sample required:
	-1ng Sample get 8 cycles 
	

**Cleanup with DCC**

- Made a 1.5mL tube for each sample, added 7:1 ratio DNA binding buffer, so 175µl of DNA binding buffer
- Put elution buffer in thermomixer 56 degrees
- Added DNA sample (25µl) to the appropriate 1.5mL tube
- Vortexed, spun down, and added to the column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Added 200µl M-wash buffer to each column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Added 200µl M-wash buffer to each column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Transferred columns to 1.5mL tubes
- Added 12.5µl warmed elution buffer to each column directly
- Incubated 1 minute
- Centrifuged 12,000 rcf 30 seconds

***Section 5: Amplification with Index Primers***
- Made new PCR tubes for each sample with 12.5µl Library Amp Mix
- Added indexed primers:
	-ACR_197 Sample got 0.5uL of Index J
	-
			*I used Index Primer J from RRBS Kit
- Added 12µl of sample to the appropriate tube (all of the flowthrough from above DCC) 
- Vortexed, spun down, and placed in theremocycler program 2nd Pico Methyl Amp program

**Cleanup with DCC**

- Made a 1.5mL tube for each sample, added 7:1 ratio DNA binding buffer, so 175µl of DNA binding buffer
- Put elution buffer in thermomixer 56 degrees
- Added DNA sample (25µl) to the appropriate 1.5mL tube
- Vortexed, spun down, and added to the column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Added 200µl M-wash buffer to each column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Added 200µl M-wash buffer to each column
- Centrifuged 12,000 rcf 30 seconds, discarded flowthrough
- Transferred columns to 1.5mL tubes
- Added 12µl warmed elution buffer to each column directly
- Incubated 1 minute
- Centrifuged 12,000 rcf 30 seconds

**D5000 TapeStation**

![ACR_197]({{ site.baseurl}}/images/20190911_PicoMethylOutcomes_ACR_197.png "ACR_197")

- [Protocol](https://meschedl.github.io/MESPutnam_Open_Lab_Notebook/DNA-Tapestation/) for D5000 tapestation followed exactly
- See [full results](https://github.com/dconetta/DAC_Putnam_Lab_Notebook/blob/master/tapestation.pdfs/2019-09-11%20-%20WGS_Prep_ACR-197.pdf)

Lastly, I Qubited the 10 samples that were going to be sent off for sequencing using the HS Assay

|Sample Id|Concentration 1| Concentration 2| Avg Concentration (ng/uL)|
|----|-----|-----|-----|
|Standard 1|NA|NA|57.56(ng/mL)|
|Standard 2|NA|NA|26415.11(ng/mL)|
|----|-----|-----|-----|
|ACR_790|4.30|4.30|4.30|
|ACR_185|2.50|2.50|2.50|
|ACR_173|22.4|22.4|22.4|
|ACR_754|7.86|7.86|7.86|
|ACR_161|9.44|9.42|9.43|
|ACR_13|1.96|1.96|1.96|
|ACR_778|4.06|4.04|4.05|
|ACR_209|3.44|3.44|3.44|
|ACR_221|13.1|13.1|13.1|
|ACR_197|8.62|8.60|8.61|

All 10 samples were shipped off on Thursday 20190912 to GenWize