# sound-wav.el [![melpa badge][melpa-badge]][melpa-link] [![melpa stable badge][melpa-stable-badge]][melpa-stable-link]

`sound-wav.el` provides play wav file. It is Emacs port of [vim-sound](https://github.com/osyo-manga/vim-sound)


## Requirements

* Emacs 24 or higher
* [deferred.el](https://github.com/kiwanami/emacs-deferred)


## Installation

`sound-wav` is available on [MELPA](https://melpa.org/) and [MELPA stable](https://stable.melpa.org/)

You can install `sound-wav` with the following command.

<kbd>M-x package-install [RET] sound-wav [RET]</kbd>

To speed up sound playing in windows, make sure
[powershell](https://msdn.microsoft.com/en-us/powershell/mt173057.aspx)
is installed, and then install the emacs package `powershell`.  This
can be done with the following command:

<kbd>M-x package-install [RET] poweshell [RET]</kbd>

When this is installed, `sound-wav` will create an shell process named
`*sound-wav-powershell*` to play sounds without needing to start
poweshell multiple times.  For me this changes a 1-2 second delay in
sounds to immediate sound processing.

## Interface

### `(sound-wav-play wav-file1 wav-file2...)`

Play wav-file1, wav-file2... . This function takes variable arguments.


## Sample Code

```lisp
;; Play wav file when file opened
(defun my/find-file-hook ()
  (sound-wav-play "somemusic.wav"))
(add-hook 'find-file-hook 'my/find-file-hook)

;; Play wav file when you start to write python
(eval-after-load "python"
  '(progn
     (sound-wav-play "somemusic.wav")))
```

[melpa-link]: http://melpa.org/#/sound-wav
[melpa-stable-link]: http://stable.melpa.org/#/sound-wav
[melpa-badge]: http://melpa.org/packages/sound-wav-badge.svg
[melpa-stable-badge]: http://stable.melpa.org/packages/sound-wav-badge.svg
