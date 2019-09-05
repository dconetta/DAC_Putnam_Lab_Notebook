---
layout: post
title: Pico Methyl Seq Kit DNA Input Testings
tags: [DNA, Methylation, BP Lengths]
---

### Testing [Zymo Pico Methyl Seq Kit](https://www.zymoresearch.com/products/pico-methyl-seq-library-prep-kit) Titrations from [Maggie's Previous Post]
(https://meschedl.github.io/MESPutnam_Open_Lab_Notebook/PMS-Test/)


Today I used the sample ACR_221, aka Tube 9, from project FACE_PUF, which is an Acropora sperm sample from Mo'orea. 
This sample was sheared to the desired BP length of 643 from [Maggie's Previous Post]
(https://meschedl.github.io/MESPutnam_Open_Lab_Notebook/Sonication-Test/)

First I quantified the amount of DNA from this sample by Qubiting it

|Sample|Total DNA|
|----|----|
|Standard 1|179.27ug/mL|
|Standard 2|19856.03ug/mL|
|221 Cap|18.3ng/uL|

Given the known DNA concentration of this sample, I then calculated the volumes of input DNA for the five input DNA concentrations of 100ng, 10ng, 1ng, 100pg, and 10pg
All input DNA for this kit required a total volume of 20uL so 

100ng of Input: 100ng/18.3 = 5.46 uL of DNA sample + 14.54uL of Ultra Pure Water

To keep all input volumes of sample ACR_221 consistent at 5.46uL I made four stocks of serial dilutions.

10ng dilution = 1uL of ACR_221 + 9uL of Ultra Pure Water ; vortex well and spin down
1ng dilution = 1 uL of 10ng dilution + 9uL of Ultra Pure Water ; vortex well and spin down
100pg dilution = 1 uL of 1ng dilution + 9uL of Ultra Pure Water ; vortex well and spin down
10pg dilution = 1 uL of 100pg dilution + 9uL of Ultra Pure Water ; vortex well and spin down

|Sample Conc|Volume of Input DNA uL| Volume of Water| Total volume for BS|
|----|----|----|----|
|100ng ACR_221|5.46uL|14.54uL|20uL|
|10ng ACR_221|5.46uL|14.54uL|20uL|
|1ng ACR_221|5.46uL|14.54uL|20uL|
|100pg ACR_221|5.46uL|14.54uL|20uL|
|10pg ACR_221|5.46uL|14.54uL|20uL|

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
  - 2µl 5X PrepAmp buffer * 4.2 = 8.4µl
  - 1µl PrepAmp Primers (40µM) * 4.2 = 4.2µl
		-For 1ng sample had to use 1uL of 20uM (0.5uL of 40uM primer + 0.5uL of Ultra Pure Water)
- Made new PCR tubes with 3µl of PrepAmp MM and 7µl of bisulfite treated DNA (100ng, 10ng, 1ng, 100pg, 10pg)
- Kept those on ice
- Made PrepAmp Mix on ice:
  - 1µl 5X PrepAmp buffer * 5.2 = 5.2µl
  - 3.75µl PrepAmp PreMix * 5.2 = 19.5uL
  - 0.3µl PrepAmp polymerase * 5.2 = 1.56µl
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
- Made a 1.5mL tube for each sample, added 7:1 ratio DNA binding buffer, so 109.2µl of DNA binding buffer and 15.6uL of Product
- Put elution buffer in thermomixer 56 degrees
- Added DNA sample (15.6µl) to the appropriate 1.5mL tube
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
 - 12.5µl 2X Library Amp Mix * 5.2 = 65.0µl
 - 1µl Library Amp Primer(10µM) * 5.2 = 5.2µl
- Added 13.5µl MM to new PCR tubes
- Added 11.5µl of cleaned and concentrated DNA sample to the appropriate new PCR tube
- Vortexed, spun down, and placed in thermocycler programs specific to how many cycles each sample required:
	-100ng Sample 6 cycles
	-10ng Sample 8 cycles
	-1ng Sample 8 cycles
	-100pg Sample 10 cycles
	-10pg Sample 10 cycles

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
	-100ng Sample got 0.5uL of Index A
	-10ng Sample got 0.5uL of Index B
	-1ng Sample got 0.5uL of Index C
	-100pg Sample got 0.5uL of Index D
	-10pg Samplegot 0.5uL of Index E
- Added 12µl of sample to the appropriate tube (all of the flowthrough from above DCC) _note, 1431 captured had more that 12µl in the tube, portentially wash buffer that did not full come out? All of that sample was added to the tube for amplification._
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
![100ng]({{ site.baseurl}}/images/20190815-ACR_221-100ng.png "100ng")

![10ng]({{ site.baseurl}}/images/20190815-ACR_221-10ng.png "10ng")

![1ng]({{ site.baseurl}}/images/20190815-ACR_221-1ng.png "1ng")

![100pg]({{ site.baseurl}}/images/20190815-ACR_221-100ng.png "100pg")

![10pg]({{ site.baseurl}}/images/20190815-ACR_221-100ng.png "10pg")


- [Protocol](https://meschedl.github.io/MESPutnam_Open_Lab_Notebook/DNA-Tapestation/) for D5000 tapestation followed exactly
- See [full results] (https://github.com/dconetta/DAC_Putnam_Lab_Notebook/blob/master/tapestation.pdfs/2019-08-15%20-%20Titrations%20(100ng-10pg).pdf)