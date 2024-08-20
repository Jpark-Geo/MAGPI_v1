# MAGPI_v1
##------------------------------------------------------------------------------------------------------------------------##
This document references and provides instructions for the program MAGPI (Method for Atmospheric Gas Partitioning from fluid Inclusions. The intent of this program is to parse out gas contributions from trapped air bubbles and brine within bulk decrepitation analyses. Accompanying this code is a blank excel sheet where raw gas compositions can be input. The program considers the solubility of the four major atmospheric gases, molecular nitrogen (N2), molecular oxygen (O2), argon (Ar), and carbon dioxide (CO2), in determining the relative contributions from each phase. Solubilities are calculated from input temperature and salinities. The program then calculates the gas volume fractions of the ruptured inclusions by comparing observed N2/Ar ratios to a user input gaseous end member. Based on the calculated gas volume fractions the program will automatically partition the gas contents and provide a new gas composition that more accurately reflects the composition of the trapped air bubbles, and not the mixture of the two phases. The program will also plot the gas results to visuallize the spread amongst the data as well as the distribution of phase volumes. MAGPI_V1 is written in python using jupyter notebook.

##------------------------------------------------------------------------------------------------------------------------##
INPUT INSTRUCTIONS: 
MAGPI_v1 requires three input parameters:
1. The temperature at which the inclusions formed (degrees celcius)
2. The salinity of the brine within the fluid inclusions (Molarity)
3. The expected atmospheric N2/Ar end member

A fourth set of parameters can be input for graphing purposes. This includes the relative partial pressure of the four major gases in the atmosphere. These are by default set to the modern atmosphere composition N2 = 0.7808, O2 = 0.2095, Ar = 0.0093, CO2 = 0.0004. Input values should be normalized to sum to 1. 

##------------------------------------------------------------------------------------------------------------------------##
ATTACHED EXCEL SPREADSHEET:
The excel spreadsheet template provides space to input raw unpartitioned gas compositions. The columns titled "Raw_N2%", "Raw_O2%","Raw_Ar%", and "Raw_CO2%" are called in the program to import the data. Please import the compositions normalized to 1. (e.g. 0.7808= 78.08%). Please keep all cells to the right of these columns empty. This is where data will be output. Anything to the left can be used. Save the file with your data and copy the file path into the program. MAGPI will read and write to the first sheet in this excel file everytime the program is run. 

##------------------------------------------------------------------------------------------------------------------------##
OUTPUT AND OPERATION:
MAGPI will perform calculations following the equations discussed in Park and Schaller (2024). The program will automatically calculate averages and standard deviations from the input data, as well as the N2/Ar ratio and gas volume fraction. Each composition will then be partitioned and the averages and standard deviations will be computed again. The program will automatically update the excel file with this information. 

GRAPHING: If an atmospheric composition is input, the program will give 2 sets of figures. 
1a. The program will plot observed N2/Ar vs the calculated gas volume fraction. It will also calculate and plot a model curve based on the input atmospheric N2/Ar
1b. The program will plot the raw and partitioned gas compositions against their index in the excel file. This will compare the average partitioned composition to the expected atmosphere.

2. Raw gas compositions are plot against gas volume fractions and are compared to modeled curves. A statistical evaluation of how well the modeled curve fits observations is performed and the results are shown on each graph. 
