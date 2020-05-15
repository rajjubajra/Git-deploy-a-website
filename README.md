
<h1>Git Deploy a website to Cpanel</h1>

<p>source: <a href="https://youtu.be/9qIK8ZC9BnU" target="_blank">Kyle Robinson Young</a></p>

e.g webserver: ssh root@example.com
<ul>
  <li>
    <p>[Set location to push and pull code to the remote server]</p>
    root@example:/var/repo# mkdir test_repo.com.git
  </li>
  <li>root@example:/var/repo# cd test_repo.com.git</li>
  <li>root@example:/var/repo/test_repo.com.git# git init --bare</li>
  <li>root@example:/var/repo/test_repo.com.git# cd hooks</li>
  <li>root@example:/var/repo/test_repo.com.git/hooks# vi post-receive</li>
  <li>[this will open Bash Shell, type following bash script in to the bash shell]</li>
  <li>#!/bin/sh<br />
    git --work-tree=/var/public_html/test_repo.com --git-dir=/var/repo/test_repo.com.git checkout -f
    <br /> [note: <i>"var/public_html/test_repo.com"</i> is where code will be deployed and <i>"var/repo/test_repo.com.git"</i> is where where code is pushed, these are two different folders]
    <br />[press 'esc' key]
    <br />[type :wq on bash shell]
  </li>
  <li>[give executable permission to the operating system]</li>
  <li>root@example:/var/repo/test_repo.com.git/hooks# chmod +x post-receive</li>
  <li>root@example:/var/repo/test_repo.com.git/hooks# exit</li>
  <li>[Now we can push code to the remote server]</li>
  <li>[Local-computer-terminal/ folder]</li>
  <li>git init</li>
  <li>[add live target to push to the remove site]</li>
  <li>git remote add live ssh://root@example.com/var/repo/test_repo.com.git</li>
  <li>[add some codes or file]</li>
  <li>git add .</li>
  <li>git status</li>
  <li>git commit -m "initial commit"</li>
  <li>git push live master</li>
  <li>[we should see the updated file in romote server]</li>
    
  </ul>
