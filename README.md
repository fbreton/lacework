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
  1. lacework event show | open present only the event with severity Critical and High for the 7 last days

     `~ lacework event show  
     
8777  8773  8781  8775  8779                    -- Type: NewViolations, Start time: 2021-07-13T13:00:00Z                                            
8999                                            -- Type: UserLaunchedNewBinary, Start time: 2021-07-14T09:00:00Z                                    
9030                                            -- Type: UserLaunchedNewBinary, Start time: 2021-07-14T13:00:00Z                                    
9046  9039  9048  9033  9035  9042  9045        -- Type: NewViolations, Start time: 2021-07-14T13:00:00Z                                            
9199                                            -- Type: UserLaunchedNewBinary, Start time: 2021-07-15T12:00:00Z                                    
9206                                            -- Type: NewExternalServerBadDns, Start time: 2021-07-15T13:00:00Z                                  
9236  9225  9230  9229  9235  9223              -- Type: NewViolations, Start time: 2021-07-15T13:00:00Z                                            
9240  9222                                      -- Type: ComplianceChanged, Start time: 2021-07-15T13:00:00Z                                        
9609  9616  9624  9618  9606  9608  9617  9622  -- Type: NewViolations, Start time: 2021-07-16T13:00:00Z                                            
9610  9615                                      -- Type: ComplianceChanged, Start time: 2021-07-16T13:00:00Z`
  3. 
