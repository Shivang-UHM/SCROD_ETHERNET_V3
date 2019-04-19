# SCROD_ETHERNET_V3
This repository contains the Ethernet module compatible with the SCROD RevA5. In it are a few example projects that can be used as a
spring board for implementing the module in your project. 

This project contains several submodules. Each submodule is a repository isolated from the main SCROD_ETHERNET_V3 repository. 
As such it is important to keep in mind that:
   1. each submodule has a remote repository separate from the main
   2. the main repository does not track changes to the submodules and vice versa
If you are unfamiliar with submodules and would like to know about them see: https://git-scm.com/book/en/v2/Git-Tools-Submodules

!!!!!PLEASE READ: HOW TO PROPERLY CLONE THIS REPOSITORY!!!!!
Step 0: If you are making modifications to the repository, PLEASE FORK IT FIRST! Any final changes you want to contribute to the 
original repository must be submitted via pull request.
        
Step 1: Clone SCROD_ETHERNET_V3 into a desired location on your PC. This is your local repository.

Step 2: Go into the local repository. Right now, only the main repository is fully populated. Run the following command to initialize
and update the submodules: git submodule update --init --recursive

Step 3: Ensure submodules are connected to their remote repositories. If they are not, you have not recieved the latest changes to the 
        submodule. Run: git submodule foreach --recursive git remote -v
        The output should match this: 
          Entering 'SCROD_ETHERNET_Example_SendBack'
          origin  https://github.com/RPeschke/SCROD_ETHERNET_Example_SendBack.git (fetch)
          origin  https://github.com/RPeschke/SCROD_ETHERNET_Example_SendBack.git (push)
          Entering 'firmware-ethernet'
          origin  https://github.com/RPeschke/firmware-ethernet.git (fetch)
          origin  https://github.com/RPeschke/firmware-ethernet.git (push)
          Entering 'firmware-ethernet/ExampleProject/firmware-general'
          origin  https://github.com/PsiStarPsi/firmware-general (fetch)
          origin  https://github.com/PsiStarPsi/firmware-general (push)
          rpeschke        https://github.com/RPeschke/firmware-general.git (fetch)
          rpeschke        https://github.com/RPeschke/firmware-general.git (push)
          Entering 'makeise'
          origin  https://github.com/RPeschke/makeise.git (fetch)
          origin  https://github.com/RPeschke/makeise.git (push)
          Entering 'vhdl_build_system'
          origin  https://github.com/RPeschke/vhdl_build_system.git (fetch)
          origin  https://github.com/RPeschke/vhdl_build_system.git (push)
          Entering 'vhdl_csv_io'
          origin  https://github.com/RPeschke/vhdl_csv_io.git (fetch)
          origin  https://github.com/RPeschke/vhdl_csv_io.git (push)
     
     Each "Entering 'submodule'" line is followed by the submodule's list of remotes: <remote name> '<url of remote>'
     If one of these remotes are not listed in your output, add them: git remote add <remote name> '<url of remote>'.
     You can fetch changes from these remotes with: git fetch <remote> <branch>. 
     
     Step 4: If you plan on modifying the one of submodules, go to the remote you want to modify, and fork it into your github. 
             Add the fork as a remote to the submodule in the local repo. Push any changes to you fork only. When you are ready
             to contribute your changes, submit a pull request.
             
 Description of submodules: 
  1. SCROD_ETHERNET_SendBack: With the udp_client.py script you can send an arbitrary command to SCROD and it will repeate it 
                              back to you. It cannot do register operations, but does prove that the s6 ethernet module is functional.
                              
  2. firmware-ethernet: contains a fuller version example project that can do register operations. 
     Warning: if you are not able to build the project, because of a gtpClk mapping error, you most likely have fetched changes from 
              an outdated remote. The affected module is: firmware-ethernet/ExampleProject/firmware-general
              Make sure you add and fetch changes from:  rpeschke https://github.com/RPeschke/firmware-general.git
   
 #other submodule descriptions to come. 
 