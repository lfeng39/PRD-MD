# Server Connect Git by SSH
- Generate SSH key on Devices

          ssh-keygen -t ed25519 -C "your_email@example.com"
- Copy SSH key from: [if no path has setted]

  -- Linux

          cd root/.ssh/
          cat id_eded25519.pub
  -- Windows
          
          cd C:\Users\username\.ssh
          cat id_eded25519.pub
- Copy SSH key and paste to git -> settings -> 'SSH and GPG keys'
  
          ssh-ed25519 %&*%^&*(*(*&*T*H(U*&TG
       

# GIT
- Clone

          git clone url
- Clone branch

          # clone latest commit
          git clone --depth 1 git@github.com:user_name/E_trade.git
          
          # clone branch with latest commit
          git clone --depth 1 --branch branch_name git@github.com:user_name/E_trade.git
- Pull & Push

          git pull origin branchName
          git add .
          git commit -m 'dir'
          git push origin branchName
- Check branch

          git branch
- Create branch

          git branch branch_name
- Change branch

          git checkout branch_name
- Delete branch

          git branch -D branch_name
- Check commit

          git reflog
- Discard local modifications

  ## Method 1
  
          git fetch --all
          git reset --hard
          git pull origin branch_name
  
  ## Method 2
  ### 2.1 discard .pyc of local modification
  
            git checkout -- app/__pycache__/ app/__pycache__/         
  ### 2.2 discard all modifications of local（becareful，that's all）
  
            git checkout -- .
          
          git pull origin branch_name
- Other
  
  -- back to one of commits that you want, ID from [reflog]
  
          git reset --hard ID
  
          git fetch --all
          git reset --hard origin branch_name
          git pull origin branch_name

          git reset --hard
          git pull origin branch_name
        
# Merge JS sources after git pull
- Run on server

          python3 manage.py collectstatic


# stable-diffusion for mac
### Step 1: Install Homebrew
First, we need to install Homebrew. Copy the following code:

        /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
        /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"export PATH=/opt/homebrew/bin:$PATH
        
### Step 2: Install Required Packages
We need to install some more packages for this to work. Next, run the following command in terminal:

        brew install cmake protobuf rust python@3.10 git wget
        
### Step 3: Install Stable Diffusion UI
Now, we’ll install the stable diffusion UI. Type and execute the following command on terminal:

        git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui

### Step 4: Add Model Files
Once the installation is complete, open the stable diffusion web UI folder

### Step 5: Launch the Web UI
In the terminal, type cd stable-diffusion-webui and then execute

        ./webui.sh
