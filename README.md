# QRSDetection
Python script to apply the Pan-Tompkins QRS detection algorhythm on ECG recordings from the PhysioNet Paroxysmal Atrial Fibrillation Challenge Database. 

The Python script uses the wfdb library with colab in order to upload records of the Paroxysmal Atrial Fibrillation Challenge Database (PAF). 
The records available in this database are the ECG signal recording of patients right before the AF episode (for 'p' prefixed files) and with no history of 
atrial fibrillation nor atrial fibrillation detection during the examination ('n' prefixed files). 

The database also gives RR intervals estimations for every recording with a automatic and not audited QRS detector. With a look on the RR intervals for some patients,
we hardly tough it was supposed to be NSR records, so we want to test a QRS detection algorhythm and see if it could lead to a better estimation of the RR intervals. 
We used the Pan-Tompkins algorithm to detect the QRS complexes, the R peaks and estimates the RR intervals for all the records. The Pan-Tompkins algorhythm is used with a
5 to 15Hz pass band filter and all the records have a 128 sampling frequency. 

So we do have 2 RR intervals estimations for each record, they sometimes diverge from each other. For some patients, we detected a few phases were the 
Pan-Tompkins RR intervals estimation were different from the PhysioNet estimation. The QRSdetection Python script provides many functions but mostly the comparison 
function to print a selected time slot of the ECG signal of a specific record with the R peak locations from Pan-Tompkins and PhysioNet algorhythms. 

The point is to see where the divergence occurs and select which one is the more appropriate. 
