# NeuroRocket
> Authors: Ratnodeep Bandyopadhyay and Shixun Wu

### Docker Setup
Install docker on your local machine.

```
docker pull qsoe/neurorocket:v0.4.1
```

```
git clone git@github.com:QuarterShotofEspresso/neurorocket.git
```

CD into the directory and checkout `qsoe/docker`

```
git checkout qsoe/docker
```

Download the InsectSound sample from UCR Archive (4GB) and execute the following command to mount both the archive and the git repo to your docker environment

```
docker run -it -v ./DNN_NeuroSim_V1.4:/home/neurorocket -v ~/ucr_archive:/root/ucr_archive qsoe/neurorocket-cpu:v0.4.1
```

```
cd /home/neurorocket/DNN_NeuroSim_V1.4/Inference_pytorch
```

```
python3 inference.py
```

### NeuroSim

- NeuroSim command

```
python inference.py --dataset InsectSound --model Rocket --mode WAGE --inference 1 --cellBit 1  --subArray 32 --parallelRead 32 
```

- NeuroSim only supports power of 2
- Modify network.csv, param.csv and compile.
