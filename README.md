# emacs-c-p

If using in screen, make sure X display forwarding is on via:
`export DISPLAY=:0`

```
(defun mycopy ()
  (interactive)
  (if (region-active-p)
      (progn
        (shell-command-on-region (region-beginning) (region-end) "xclip -selection clipboard &> /dev/null")
        (message "Yanked region to clipboard!")
        (deactivate-mark))
    (message "No region active; can't yank to clipboard!")))

(global-set-key [f8] 'mycopy)
```
