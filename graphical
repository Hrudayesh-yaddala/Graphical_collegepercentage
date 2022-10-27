import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
w=0.4
#enter year
cod='21 2'.split()
#ay=enter academic year
ay=int(cod[1])
ppercentage=[]
fpercentage=[]
try:
  if(ay<1 or ay>4):
    print('enter valid academic year')
    exit()
  if(int(cod[0])==19):
    branch={0:'CIV',1:'CSE',2:'ECE',3:'EEE',4:'IT',5:'MEC'}
  elif(int(cod[0])==20):
    branch={0:'AID',1:'CIC',2:'CIV',3:'CSE',4:'CSM',5:'CSO',6:'ECE',7:'EEE',8:'IT',9:'MEC'}
  elif(int(cod[0])==21):
    branch={0:'AID',1:'AIM',2:'CIC',3:'CIV',4:'CSE',5:'CSM',6:'CSO',7:'ECE',8:'EEE',9:'IT',10:'MEC'}
  # elif(int(cod[0:2])==22):
  for i in range(len(branch)):
    df=pd.read_json('D:\\visual\\'+cod[0]+'BQ\\'+branch[i]+'.json')
    pp=0
    fp=0
    dc=0
    for i in range(2):
        sem=str(ay)+'-'+str(int(i+1))
        if(sem not in df):
            dc+=1
            continue
        pp+=df.loc['pass_percentage'].at[sem]
        fp+=df.loc['fail_percentage'].at[sem]
    if(dc==0):
        ppercentage.append(round(pp/2,2))
        fpercentage.append(round(fp/2,2))
    elif(dc==1):
        ppercentage.append(round(pp,2))
        fpercentage.append(round(fp,2))
    else:
        print("given academic year results still not yet released")
        exit()
  print(ppercentage)
  print(fpercentage)  
  #x=list(branch.values())
  b1=np.arange(len(branch))
  b2=[i+w for i in b1]
  plt.bar(b1,ppercentage,w,label='fail_percentage')
  plt.bar(b2,fpercentage,w,label="pass_percentage")
  #fig = plt.figure(figsize=(8, 8))
  plt.xlabel('departments')
  plt.ylabel('percentage')
  plt.xticks(b1,list(branch.values()))
  plt.legend()
  plt.title(f'Analysis of academic year {ay} for batch {cod[0]}BQ')
  plt.show()
except Exception as e:
  print(f'error occured in program {e}')