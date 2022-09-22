## 1. Install

- Firstly, you need install anaconda (follow this link [here](https://linuxhint.com/install-anaconda-ubuntu-22-04/))
- Check your version cuda tool you want to install with pytorch and then install cuda via  ``pip`` by command ```pip install cuda-python```
- Then you can install pytorch based on your OS and hardware [here](https://pytorch.org/get-started/locally/)


## 2. About server command

- Connect to server:

```
$ ssh -i ~/.ssh/labserver.pem longvuduc@192.168.100.131
```
  
- Some useful command in server env
```
$ byobu
=> Keep current process running when moving out
```

```
$ htop
=> check usage of disk, ram, gpu for each user using server.

$ htop -u [USER_NAME]
=> trach cpu/ram usage for specify user
```

```
$ watch nvidia-smi
=> track GPU usage
```

```
$ df -h
=> Track SSD and HDD usage
/dev/sda2 SSD: mounted on /
/dev/mdo mounted on /mnt/md0
```

```
$ ncdu [path/to/folder]
=> track individual storage usage
=> With data > 10GB, not save in main disk, using mount
/mnt/ssd4t
/mnt/md0
```

## 3. Install env and jupyter notebook in server.

- To using jupyter notebook for server firstly you need to install `ipykernel` via pip.
- Then install `jupyter notebook` module
- You need create your own kernel by command ```python -m ipykernel install --user -name=labtest``` 
- After create your own kernel => go to terminal and type `jupyter notebook` to launch. In the jupyter window -> remind choose your kernel.

## 4. About tensorboard.

- Tensor board is a visualization toolkit for machine learning or deep learning experimentation. It track and visualize metrics such as loss and accuracy, visualize model graph, view histograms, display image and more.
- To use `Tensorboard` firstly you need tho install via commmand ```$ pip install torch torchvision```
- Using Tensorboard with Pytorch we need to create a `SummaryWriter` instance
- To run TensorBoard: 
  ```
  # First you need install tensorboard
  $ pip install tensorboard

  # Start tensorboard
  $ tensorboard --logdir=runs
  ```
- Share TensorBoard dashboards
  
  ```
  # Install the latest version of tensorboard to use the uploader
  $ pip install tensorboard --upgrade

  # Upload and share your tensorboard
  $ tensorboard dev upload --logdir runs --name <name_log_runs> --description <description_about_log>
  ```
