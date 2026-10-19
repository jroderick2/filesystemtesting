# How to submit filesystem testing jobs via condor
## Step 1:
- Put your xRootD log files in a folder called "xrdlogs"
## Step 2: 
Write two txt files -
- One with a list of all the files you want to run replays over
- xrdlogs_list.txt with a list of xrootd logs you want to simulate
## Step 3:
- Modify "run_multiple.jdl" (the condor submission script) to reflect the arguments you want the replay script to take (line 7)\
  -w: the number of workers/threads you want each replay to use\
  -j: the total number of condor jobs you plan to submit\
  -r: the name of your txt file that lists the rootfiles\
  -n: turn on random reads function
## Step 4:
- Submit condor jobs using condor_submit run_multiple.jdl (make sure to have run voms-proxy-init first!)
