Documentation of BrainCorporation Filter
==== 

Brief Description 
-------
This is a project including two filters.\
The frist one is range filter. ([0.03, 50])\
The second one is temporal median filter.


API Documentation 
-------
>### bin
Executable files.
>### BrainCorp
Main files.
>>#### test
>>>##### test.py
This is the test file of the filter.\
The input are a set of float numbers listed in test_input.csv and test_result.csv.\
This function will call validate.py to validate the result.
>>>##### validate.py
This is a function used to test whether the result is equal to what we expect.\
The expected values are listed in test_result.csv.
>>#### brain.py
This function define the two filters.\
\
The input of the range filter is a set of measured distance.\
Its output is a set of distance ranged in [0.03.50].\
\
The input of the temporal median filter is a set of current scan, a set of previous scan and a number D that means we will calculate the median of previous D scans.\
Its out are median of the previous D scans and prevous D set scans.
>>#### main.py
The entry of the test file.
>>#### data
>>>##### test_input.csv
The input data.
>>>##### test_result.csv
The expected output data, which will be used to validate the correctness of the filters.
>### docs
Docutation of this project.
>### README.md
Description file.
>### requirements
External libraries used in the project.
>### setup.py
Setup files.

Test Correctness 
-------
>### Range Filter
Case1\
input:[.001,20.,4.,100.,200.]\
output:[.03, 20., 4., 50., 50.]\
Case2\
input:[-.03,-209.,432.2,10.,22.,100.,98.]\
output:[0.03, 0.03, 50., 10., 22., 50., 50.]\
Case3\
input:[.0,204.,.0003]\
output:[0.03, 50., 0.03]\
\
SUCCESS: 3/3\
FAIL: 0/3
>### Temporal Median Filter
Case1\
input:[0.,1.,2.,1.,3.],[0.5,3.,4.5,1.,3.], D = 3\
output(median):[.03, 20.,4.,50.,50.]\
Case2\
input:[2.,3.,4.,1.,0.],[3.,3.,3.,1.,3.],[10.,2.,4.,0.,0.],[0.,1.,2.,1.,3.], D = 2\
output(median):[2.,3., 4.,1.,0.],[2.5,3.,3.5,1.,1.5],[3.,3.,4.,1.,0.],[3.,2.,3.,1.,3.]\
Case3\
input:[1.,5.,7.,1.,3.],[2.,3.,4.,1.,0.],[3.,3.,3.,1.,3.],[0.,1.,2.,1.,3.],[1.,5.,7.,1.,3.],[2.,3.,4.,1.,0.],[3.,3.,3.,1.,3.], D = 5\
output(median):[1.,5.,7.,1.,3.],[1.5,4.,5.5,1.,1.5],[2.,3.,4.,1.,3.],[1.5,3.,3.5,1.,3.],[1.,3.,4.,1.,3.],[1.5,3.,4.,1.,3.],[2.,3.,3.5,1.,3.]\
\
SUCCESS: 3/3\
FAIL: 0/3

Version  
-------
> Time: 02/18/2019\
> Version: 1.0

Contact 
-------
Author: Kai Wang\
E-mail: wangjinjie722@gmail.com
