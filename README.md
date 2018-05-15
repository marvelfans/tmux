# tmux

## 复制粘贴
* 默认情况下，tmux复制的内容不能和外部共享。
    * 在`iTerm2`中，通过`iTerm2` -> `Preferences` -> `Selection` -> `Application in terminal may access clipboard`, 勾上就可以了。

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
    * `Prefix + [`，进入选择模式
    * `Space`， 开始先择
    * `Enter`, 选择完毕
    * `Prefix + ]` 将选择的内容粘贴
