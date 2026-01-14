```
# yaml-language-server: $schema=https://raw.githubusercontent.com/cooperspencer/gickup/refs/heads/main/gickup_spec.json
# (for vscode)
#
#----------------------------------------
# this is the gickup config file
# see the example file for all options
#----------------------------------------
#
# NOTE: to do multiple sources from github
#       split each out with a leading ---
#       before the second/third/etc. stanza
#
# not specifying user or username gets everything the token can access
#
# user     = who to get from
# username = who to get it as
# for help see https://gickup.dev/configuration/source_docu/github

#----------------------------------------
# get all my repos
# excluding orgs I'm a member of
# which we will list separately below
#----------------------------------------

source:
  github:
    - token_file: /Users/Vince/.ssh/pat-github
      username: vinceskahan
      excludeorgs: 
        - tomdotorg
        - weewx
        - weewx-contrib
      wiki: true
destination:
  local:
    - path: /Users/vince/Desktop/gickups
      structured: true
 
#----------------------------------------
# only 'my' weewx-contrib stuff
# THESE NEED LISTING EXPLICITLY !!!
#
# note 'username' used below to be able
# to get private repos too
#----------------------------------------

---
source:
  github:
    - token_file: /Users/Vince/.ssh/pat-github
      username: weewx-contrib
      include:
        - .github
        - admin-items
        - README-FIRST
        - broadcastWeatherFlowUDP
        - lastrain-extension
        - mem-extension
        - membership-request
        - stackedwindrose-extension
        - weewx-realtime_gauge-data
      wiki: true
      issues: true
destination:
  local:
    - path: /Users/vince/Desktop/gickups
      structured: true

#----------------------------------------
# weatherflow driver
#----------------------------------------

#---
# source:
#   github:
#     - token_file: /Users/Vince/.ssh/pat-github
#       user: captain-coredump
#       exclude:
#       include:
#         - weatherflow-udp
#       excludeorgs:
#       wiki: true
# destination:
#   local:
#     - path: /Users/vince/Desktop/gickups
#       structured: true
 
#----------------------------------------
# belchertown skin
#----------------------------------------
 
# ---
# source:
#   github:
#     - token_file: /Users/Vince/.ssh/pat-github
#       user: podlabs
#       exclude:
#       include:
#         - weewx-belchertown
#       excludeorgs:
#       wiki: true
# destination:
#   local:
#     - path: /Users/vince/Desktop/gickups
#       structured: true
 
#----------------------------------------
# matthew wall stuff
#----------------------------------------
 
# ---
# source:
#   github:
#     - token_file: /Users/Vince/.ssh/pat-github
#       user: matthewwall
#       exclude:
#       include:
#         - weewx-sdr
#         - weewx-interceptor
#         - weewx-mqtt
#         - weewx-forecast
#       excludeorgs:
#       wiki: true
# destination:
#   local:
#     - path: /Users/vince/Desktop/gickups
#       structured: true
# 
#  
#----------------------------------------
# explicitly get the weewx stuff
#----------------------------------------
 
# ---
# source:
#   github:
#     - token_file: /Users/Vince/.ssh/pat-github
#       user: weewx
#       exclude:
#       include:
#       excludeorgs:
#       wiki: true
# destination:
#   local:
#     - path: /Users/vince/Desktop/gickups
#       structured: true
 
#----------------------------------------
# weatherflow driver
#----------------------------------------

# ---
# source:
#   github:
#     - token_file: /Users/Vince/.ssh/pat-github
#       user: captain-coredump
#       exclude:
#       include:
#         - weatherflow-udp
#       excludeorgs:
#       wiki: true
# destination:
#   local:
#     - path: /Users/vince/Desktop/gickups
#       structured: true
 
#----------------------------------------
# belchertown skin
#----------------------------------------

# ---
# source:
#   github:
#     - token_file: /Users/Vince/.ssh/pat-github
#       user: podlabs
#       exclude:
#       include:
#         - weewx-belchertown
#       excludeorgs:
#       wiki: true
# destination:
#   local:
#     - path: /Users/vince/Desktop/gickups
#       structured: true
 
#----------------------------------------
# matthew wall stuff
#----------------------------------------

# ---
# source:
#   github:
#     - token_file: /Users/Vince/.ssh/pat-github
#       user: matthewwall
#       exclude:
#       include:
#         - weewx-sdr
#         - weewx-interceptor
#         - weewx-mqtt
#         - weewx-forecast
#       excludeorgs:
#       wiki: true
# destination:
#   local:
#     - path: /Users/vince/Desktop/gickups
#       structured: true
#



#---------------------------------
# example from author
#---------------------------------
# source:
#   github:
#     - token: some-token
#     # alternatively, specify token in a file, relative to current working directory when executed.
#       # token_file: token.txt
#       user: some-user # the user you want to clone the repositories from.
#       # if you want to get everything from your user, leave out the user parameter and just use the token.
#       # for the clone process, either use:
#       # - username + password
#       # - sshkey
#       # - token
#       username: your-user # user is used to clone the repo with
#       password: your-password
#       ssh: true # can be true or false
#       sshkey: /path/to/key # if empty, it uses your home directories' .ssh/id_rsa
#       exclude: # this excludes the repos "foo" and "bar"
#         - foo
#         - bar
#       include: # this includes the repo "foobar"
#         - foobar
#       excludeorgs: # this excludes repos from the organizations "foo" and "bar"
#         - foo
#         - bar
#       includeorgs: # this includes repos from the organizations "foo1" and "bar1"
#         - foo1
#         - bar1
#       wiki: true # includes wiki too
#       issues: true # back up issues, works only locally
#       starred: true # includes the user's starred repositories too
#       filter:
#         stars: 100 # only clone repos with 100 stars
#         lastactivity: 1y # only clone repos which had activity during the last year
#         excludearchived: true 
#         languages: # only clone repositories with the following languages
#           - go
#           - java
#         excludeforks: true # exclude forked repositories
#       gists: true # clone gists too
#---------------------------------
#
```  
