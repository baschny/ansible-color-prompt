Bash Color Prompt
=========

Overrides the bash shell prompt and makes it easy to set a custom color scheme per host or per group.

It configures a `profile.d` script which sets the prompt depending on chosen schema.

Usage
---

Inventory:
```
[dev:vars]
color_prompt_addon=dev
color_prompt_schema=dev

[prod:vars]
color_prompt_addon=live
color_prompt_schema=prod

[dev]
dev-server1 color_prompt_addon=dev-feature1
dev-server2

[prod]
live-server
```

Playbook:
```
  roles:
    - color-prompt
```

Options
---

See defaults for configuration options when including this role. The main ones are:

`color_prompt_schema`


* `dev`: for dev machines, green prompt, indicating no danger
* `test`: for test or staging machines, yellow prompt
* `prod`: for productive systems, red prompt, danger when doing anything

`color_prompt_addon`

A string to include to the prompt to identify the "environment" you are working
with. I.e. `dev` or `staging` or `upgrade-test`.

License and inspiration
---

Inspired by https://github.com/prgmrcom/ansible-bash-color-prompt.

License: GPLv3
