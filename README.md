# AmBe_GeSim_full_spectrum_remote_noW
Geant4 simulations of AmBe full spectrum for the source in remote position without outer tungsten capsule in UA's GeIII detector based on GeSim code by Raymond Tsang, rhmtsang@gmail.com. Read https://github.com/rhmtsang/GeSim/blob/master/README.md for more information about GeSim.  

Prerequisite: Geant 4.10.04.p02 and ROOT 5.34/07 (later versions are ok)

Author: Mariia Fedkevych, mariia.fedkevych@gmail.com

1. Download and unpack the GeSim_AmBe_full_spectrum_remote_noW.tar.gz archive, e.g. run "tar -xf GeSim_AmBe_full_spectrum_remote_noW.tar.gz" in Linux terminal
2. Source setup scripts for Geant4, e.g.

source /usr/local/geant4.10.04.p02/bin/geant4.sh
source /usr/local/geant4.10.04.p02/share/Geant4-10.4.2/geant4make/geant4make.sh

3. Go to the GeSim_AmBe_full_spectrum_remote_noW folder and run "cmake ."
4. Compile with "make -f Makefile"
5. Prepare an HEPEvt format generator file for AmBe gamma spectrum (from "am241be.spectrum") which will be read by capsule_emissionV2: 
    - make an executable of am241be.cc, e.g. run "g++ am241be.cc -o am241be.exe" 
    - run the executable with the number of events to be generated and the output file name "generator.data", e.g. "./am241be.exe 10000000 > generator.data"
6. Before starting the simulations, run "export AllowForHeavyElements=1"
7. The simulations can be executed by running "./GeSim AmBe.mac"
8. The output root file containing energy distributions of primary and detected gammas will be generated within the same folder (the name is set in AmBe.mac). 
9. If you didn't comment out the visualization options in AmBe.mac, it will generate .wrl file in the same folder. 
