### clone all branches in 5 steps

`mkdir filter-branch-test`

`cd filter-branch-test`

`git clone --bare https://github.com/darren-lu/filter-branch-test.git .git`

`git config --bool core.bare false`

`git reset --hard`

---

### git fitler-branch

`git filter-branch --force --index-filter \ 'git rm --cached --ignore-unmatch
config/c.txt' \--prune-empty --tag-name-filter cat -- --all`

#### output:

```
Rewrite a6308b65052b92f31391d0fe826bc68df2dfbaae (1/8) (0 seconds passed, remaining 0 predicted)    rm 'config/c.txt'
Rewrite 5a12add6569b361c1c574009133ea0eca105a5cb (2/8) (0 seconds passed, remaining 0 predicted)    rm 'config/c.txt'
Rewrite 422b395764281ca74a0769acf78a2e7d47e7d606 (3/8) (0 seconds passed, remaining 0 predicted)    rm 'config/c.txt'
Rewrite f21f1bd42bbfff3d1787f69e3b7cb3986ac64716 (4/8) (0 seconds passed, remaining 0 predicted)    rm 'config/c.txt'
Rewrite a097ea3ca2e2c69c2fb7e04c89331118b2d6d4a5 (5/8) (0 seconds passed, remaining 0 predicted)    rm 'config/c.txt'
Rewrite 847f1008c451a77a3f8e719bc97b0e589c462790 (6/8) (0 seconds passed, remaining 0 predicted)    rm 'config/c.txt'
Rewrite e2152af17c08529de42adc26640a5a746cb35dec (7/8) (0 seconds passed, remaining 0 predicted)    rm 'config/c.txt'
Rewrite 4a520484575f5112e901914f33e57c7535fd342e (8/8) (0 seconds passed, remaining 0 predicted)    rm 'config/c.txt'

Ref 'refs/heads/backup' was rewritten
Ref 'refs/heads/master' was rewritten
```

Double-check if `config/c.txt` exist in `master` and `backup` branches.

---

### reference

[#using-filter-branch](https://help.github.com/articles/removing-sensitive-data-from-a-repository/#using-filter-branch)

