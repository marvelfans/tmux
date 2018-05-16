# tmux


## 基本用法
前提: `Prefix = Ctrl + b`
* `tmux new-session -s <session-name>`: 创建一个tmux session
    * `Prefix + ,` 修改tmux session中，window的名字。
    * `Prefix + c` 在tmux session中，创建一个新的窗口。
    * `Prefix + h` 在tmux session中的window中，水平分割。在.tmux.conf中做了键的绑定。
    * `Prefix + v` 在tmux session中的window中，垂直分割。在.tmux.conf中做了键的绑定。
* `tmux detach` 从tmux session中退出，保存session的状态。
* `tmux attach-session -t <session-name>` 恢复tmux session。
* 复制粘贴      <b>Tip::可以参考Emacs的复制粘贴。</b>
    * 默认情况下，tmux复制的内容不能和外部共享。
        * 在`iTerm2`中，通过`iTerm2` -> `Preferences` -> `Selection` -> `Application in terminal may access clipboard`, 勾上就可以了。
    * `Prefix + [`，进入选择模式
    * `Space`， 开始先择
    * `Enter`, 选择完毕
    * `Prefix + ]` 将选择的内容粘贴
    * 移动可以使用vi的方式

## vim 在tmux下显示不全的问题
* 是由于tmux不支持256color导致的。
* 在~/.tmux.conf中添加: `set -g default-terminal "screen-256color"`
* 然后在启动tmux时候，使用`-2`参数，为此我在`.zshrc`中做了以下绑定
    ```
    alias tmux='/usr/local/bin/tmux -2 '
    alias tmux-new='/usr/local/bin/tmux -2 new-session -s'
    alias tmux-detach='/usr/local/bin/tmux detach'
    alias tmux-attach='/usr/local/bin/tmux -2 attach-session -t'
    alias tmux-kill='/usr/local/bin/tmux kill-session -t'
    alias tmux-ls='/usr/local/bin/tmux ls'
    ```
