# Server Connect Git by SSH
### Generate SSH key on Devices

          ssh-keygen -t ed25519 -C "your_email@example.com"
### Copy SSH key from: [if no path has setted]

  -- Linux

          cd root/.ssh/
          cat id_eded25519.pub
          
          cat ~/.ssh/id_ed25519.pub（terminal mad）
  -- Windows
          
          cd C:\Users\username\.ssh
          cat id_eded25519.pub

          cat ~/.ssh/id_ed25519.pub（terminal mad）
  -- Mac

          pbcopy < ~/.ssh/id_ed25519.pub
### Copy SSH key and paste to git -> settings -> 'SSH and GPG keys'
  
#### ex: ssh-ed25519 %&*%^&*(*(*&*T*H(U*&TG
#### copy command:
  -- Linux / Windows:
          
          cat ~/.ssh/id_ed25519.pub
  -- Mac:
          
          pbcopy < ~/.ssh/id_ed25519.pub

# GIT
### Clone

          git clone url
### Clone branch

          # clone latest commit
          git clone --depth 1 git@github.com:user_name/E_trade.git
          
          # clone branch with latest commit
          git clone --depth 1 --branch branch_name git@github.com:user_name/E_trade.git
### Pull & Push

          git pull origin branchName
          git add . / git add folde/file
          git commit -m 'dir'
          git push origin branchName
### Manage Version
##### 1) Create local new_branch & remote new_branch

          git checkout -b new_branch_name
          git add . / git add folde/file
          git commit -m 'new branch'
          git push -u origin new_branch_name
#### 2) Commit & Push new code

          git add . / git add folde/file
          git commit -m 'update ***'
          git push
#### 3) Checkout branch main & merge new_branch

          git checkout main
          git merge new_branch_name
          git push origin main
#### 4）Tag Version(on branch main)

          git tag version_number
          git push origin version_number
#### 5) Del branch & Repeat

          git branch -d new_branch_name
          git push origin --delete new_branch_name
### Check branch

          git branch
### Create branch & Create remote branch

          git branch branch_name
          git push -u origin branch_name
### Change branch

          git checkout branch_name
### Delete branch

          git branch -D branch_name
### Check commit

          git reflog
### Discard local modifications

- Method 1

-- 1.1

          git fetch --all
          git reset --hard
          git pull origin branch_name

- Method 2

-- 2.1 discard .pyc of local modification

          git checkout -- app/__pycache__/ app/__pycache__/         
-- 2.2 discard all modifications of local（becareful，that's all）
  
          git checkout -- .
          git pull origin branch_name
### Other
  
- back to one of commits that you want, ID from [reflog]
  
          git reset --hard ID
  
          git fetch --all
          git reset --hard origin branch_name
          git pull origin branch_name

          git reset --hard
          git pull origin branch_name
        
# Merge JS sources after git pull on server
### Run on server

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
