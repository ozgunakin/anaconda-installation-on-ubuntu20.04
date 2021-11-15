# Anaconda Installation on Ubuntu20.04

This is a guide for Anaconda installation on Ubuntu 20.04

## Step 1 - Create a Download Repository

Create a download repository to save the Anaconda installer.

```
mkdir downloads
cd downloads
```

## Step 2 - Download Anaconda

Check the latest version on [https://www.anaconda.com/distribution/](https://www.anaconda.com/distribution/) before running the code. If there is a newer release you can change the download link.

```
wget https://repo.anaconda.com/archive/Anaconda3-2021.05-Linux-x86_64.sh
```

## Step 3 - Edit File Permissions

You need to give execute permission to the users, to be able to run the Anaconda3-xxx-xxx.sh file.

```
sudo chmod +x Anaconda3-2021.05-Linux-x86_64.sh
```

You also need to change the owner of the directory you select for anaconda installation. (or you can give permission to your user on this directory). The selected directory is "/data" for our case.

```
sudo chown -R ozgunakn:ozgunakn /data
```

## Step 4 - Run Anaconda.sh (Installing)

Go to the download directory and run Anaconda-xxx-xxx.sh file.

```
cd downloads
./Anaconda3-2021.05-Linux-x86_64.sh
```

* It will suggest you an installing directory, you can change it. In our case, I typed "/data/anaconda3" as installing directory.
* After installation, it will ask you, whether you want to run initialize or not. You can type YES.

You need to source .bashrc file after installation.

```
cd
source .bashrc
```

If the base conda environment automatically is opened, you are good to go! If it is not you can repeat the steps above.

## Step 5 - Activate Conda Forge

It is important to activate conda-forge to be able to install additional packages.

```
conda config --add channels conda-forge
```

## Hint!

You can search packages and versions on anaconda using the code below

```
conda search airflow
```

After installation anaconda base environment will be automatically activated for each session of your user. To disable automatic activation;

```bash
conda config --set auto_activate_base false
```
