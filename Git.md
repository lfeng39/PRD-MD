# GIT
        git get code step
                git clone url
        git post code step
                git pull origin branchName
                git add .
                git commit -m 'dir'
                git push -u origin branchName
        other
                git fetch --all
                git reset --hard origin/分支名
                git pull
                【放弃本地修改，直接覆盖】
                git reset --hard
                git pull
        

# stable-diffusion for mac
## Step 1: Install Homebrew
        First, we need to install Homebrew. Copy the following code:
                /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
        
        Step 2: Install Required Packages
        We need to install some more packages for this to work. Next, run the following command in terminal:
                brew install cmake protobuf rust python@3.10 git wget
        
        Step 3: Install Stable Diffusion UI
        Now, we’ll install the stable diffusion UI. Type and execute the following command on terminal:
                git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui

        Step 4: Add Model Files
        Once the installation is complete, open the stable diffusion web UI folder
