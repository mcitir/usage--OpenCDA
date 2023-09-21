#Install carla module
First check version, `pip show carla`, if it is not satisfied install again with specific version `pip install carla==0.9.12`

export location for carla:
```
export CARLA_HOME=$HOME/Workspace/CARLA_0.9.12
export CARLA_VERSION=0.9.12
```

## Common Errors
### 1. Mismatch of versions

![image](https://github.com/mcitir/usage--OpenCDA/assets/35730346/f6f22f1c-380e-48f6-aedf-975c95b6d2f0)

#### Re-apply steps
1) make setup
2) make LibCarla
3) make CarlaUE4Editor
4) make launch
5) make PythonAPI
6) easy_install --user --no-deps PythonAPI/carla/dist/carla-0.9.11-py3.8-linux-x86_64.egg (DOES NOT WORK)

But , I realized, CARLA_ROOT was defined as ../carla/. So, this makes /carla//PythonAPI/..

I corrected as below:

![image](https://github.com/mcitir/usage--OpenCDA/assets/35730346/31f3c5f7-14f6-4e27-9448-1eb7f79e22fa)

7) I checked, whether they are correct:
export CARLA_HOME=/path/to/your/CARLA_ROOT
export CARLA_VERSION=0.9.11 #or 0.9.12 depends on your CARLA
8) Then, link .egg from carla to OpenCDA:
. setup.sh
9) I tested it: python opencda.py -t single_2lanefree_carla -v 0.9.11
### Result:
No need to implement Step 8 (setup.sh). Without doing that, still working.

