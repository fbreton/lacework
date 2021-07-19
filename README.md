# Completion for lacework
This script is to be use with zsh and can be use with Oh My Zsh framework to get lacework command completion.
Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration that you can get from https://ohmyz.sh/

 
You also need to have jq installed: https://github.com/stedolan/jq/wiki/Installation

## Instalation
To use the lacework completion with Zsh (without Oh My Zsh):
  1. Just drop the file in one of your function folders that you can find looking in fpath: `echo $fpath`

To use the lacework completion with Oh My Zsh you need to:
  1. create directory ~/.oh-my-zsh/custom/plugins/lacework
  2. copy the file in _lacework in the directory ~/.oh-my-zsh/custom/plugins/lacework
  3. edit your ~/.zshrc file, find the line starting by plugins to add lacework to the plugins list, you should at least have: 

    plugins=(... lacemork)
 
This has been tested with cli version 0.9.1

## Information on some completion
Only the following flags support the completion:
  1. -p to switch between profile
  2. --subaccount to switch between account inside your organisation

For some command the completion present only subset of possibilities:
  1. `lacework event show | open` present only the event with severity Critical and High for the 7 last days

        `~ lacework event show`
     
        8777  8773  8781  8775  8779                    -- Type: NewViolations, Start time: 2021-07-13T13:00:00Z                                            
        8999                                            -- Type: UserLaunchedNewBinary, Start time: 2021-07-14T09:00:00Z                                    
        9030                                            -- Type: UserLaunchedNewBinary, Start time: 2021-07-14T13:00:00Z                                    
        9046  9039  9048  9033  9035  9042  9045        -- Type: NewViolations, Start time: 2021-07-14T13:00:00Z                                            
        9199                                            -- Type: UserLaunchedNewBinary, Start time: 2021-07-15T12:00:00Z                                    
        9206                                            -- Type: NewExternalServerBadDns, Start time: 2021-07-15T13:00:00Z                                  
        9236  9225  9230  9229  9235  9223              -- Type: NewViolations, Start time: 2021-07-15T13:00:00Z                                            
        9240  9222                                      -- Type: ComplianceChanged, Start time: 2021-07-15T13:00:00Z                                        
        9609  9616  9624  9618  9606  9608  9617  9622  -- Type: NewViolations, Start time: 2021-07-16T13:00:00Z                                            
        9610  9615                                      -- Type: ComplianceChanged, Start time: 2021-07-16T13:00:00Z

  2. `lacework vulnerability host list-host` present only the CVEs that are active and contains critical and high severities

      `~ lacework vulnerability host list-hosts
ALAS-2019-1258                                   -- OS: amzn:2018.03; #Host: 1; #Critical: null; #High: 4                                           
ALAS2-2019-1258                                  -- OS: amzn:2; #Host: 1; #Critical: null; #High: 3                                                 
ALAS2-2021-1654                                  -- OS: amzn:2, amzn:2; #Host: 6; #Critical: null; #High: 6                                         
CVE-2017-8779                                    -- OS: rhel:6; #Host: 1; #Critical: null; #High: 3                                                 
CVE-2018-1111                                    -- OS: centos:7, rhel:6; #Host: 2; #Critical: 8; #High: null                                       
CVE-2018-16864   CVE-2018-16865  CVE-2018-15688  -- OS: centos:7; #Host: 1; #Critical: null; #High: 3                                               
CVE-2018-5732                                    -- OS: rhel:6; #Host: 1; #Critical: null; #High: 2                                                 
CVE-2019-12749                                   -- OS: centos:7, rhel:7; #Host: 3; #Critical: null; #High: 8                                       
CVE-2019-17042   CVE-2019-17041                  -- OS: debian:10; #Host: 2; #Critical: null; #High: 1                                              
CVE-2019-6454                                    -- OS: centos:7; #Host: 1; #Critical: null; #High: 6                                               
CVE-2020-12049                                   -- OS: rhel:7, centos:7; #Host: 3; #Critical: null; #High: 6                                       
CVE-2020-25097                                   -- OS: rhel:7; #Host: 1; #Critical: null; #High: 4                                                 
CVE-2021-25217                                   -- OS: rhel:7, rhel:6, centos:7; #Host: 4; #Critical: null; #High: 11`

 3.
