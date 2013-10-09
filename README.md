# sound-wav.el

`sound-wav.el` provides play wav file. It is Emacs port of [vim-sound](https://github.com/osyo-manga/vim-sound)


## Requirements

* Emacs 24 or higher
* [deferred.el](https://github.com/kiwanami/emacs-deferred)


## Sample Code

```elisp
;; Play wav file when file opened
(defun my/find-file-hook ()
  (sound-wav-play "somemusic.wav"))
(add-hook 'find-file-hook 'my/find-file-hook)

;; Play wav file when you start to write python
(eval-after-load "python"
  '(progn
     (sound-wav-play "somemusic.wav")))
```
