# Server Connect Git by SSH
- Generate SSH key on Devices

          ssh-keygen -t ed25519 -C "your_email@example.com"
- Copy SSH key from: [if no path has setted]

          cat ~/.ssh/id_ed25519.pub 
- Copy SSH key and paste to git -> settings -> 'SSH and GPG keys'
  
        ssh-ed25519 %&*%^&*(*(*&*T*H(U*&TG
       

# GIT
- clone

        git clone url
- pull & push

        git pull origin branchName
        git add .
        git commit -m 'dir'
        git push origin branchName
- check branch

          git branch
- create branch

          git branch branch_name
- change branch

          git checkout branch_name
- delete branch

          git branch -D branch_name
- Check commit

          git reflog
- other
-- Check histroy
  
          git reflog
  -- back to some version that you want []
  
          git reset --hard ID
  
          git fetch --all
          git reset --hard origin branch_name
          git pull origin branch_name

          git reset --hard
          git pull origin branch_name
        

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
