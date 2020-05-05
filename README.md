# Git-deploy-a-website

<h1>Git Deploy a website</h1>
e.g webserver: ssh root@example.com
<ul>
  <li>
    <p>Set location to push and pull code to the remote server</p>
    root@example:/var/repo# mkdir test_repo.com.git
  </li>
  <li>root@example:/var/repo# cd test_repo.com.git</li>
  <li>root@example:/var/repo/test_repo.com.git# git init --bare</li>
  <li>root@example:/var/repo/test_repo.com.git# cd hooks</li>
  <li>root@example:/var/repo/test_repo.com.git/hooks# vi post-receive</li>
  <li>[this will open Bash Shell, type following bash script in to the bash shell]</li>
  <li>#!/bin/sh<br />
    git --work-tree=/var/public_html/test_repo.com --git-dir=var/repo/test_repo.com.git checkout -f
  </li>
  <li></li>
  </ul>
