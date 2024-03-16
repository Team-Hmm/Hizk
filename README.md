[Hizk - GPT-4���ڂ́u�Ӗ�����ϊ�����v������IME](https://github.com/Team-Hmm/Hizk)
===================================
Copyright 2010-2024 Google LLC  
Copyright 2024-2024 kokastar,YukkuriPanda 

System Requirements
-------
64bit Windows10�ȍ~���T�|�[�g���܂��B  
Linux��MacOS�ł͓��삵�܂���B  
�܂��A�r���h���ɏ\���ȃX�g���[�W�e�ʂ��K�v�ƂȂ�܂��B  

�v���O�����̎d�l��g���C�̖ؔn�Ɠ������������邽�߁A�E�C���X�΍�\�t�g�ɂ���Ă͌댟�m����邱�Ƃ�����܂��B���̏ꍇ�́A�E�C���X�΍�\�t�g�̐ݒ��ύX���邩�A���̃\�t�g�E�F�A���g�p���Ȃ��ł��������B

How to Use
-------
How to Build �̏͂ɏ]���r���h���s���Ă��������B    
���̌㐶�������.msi�t�@�C�������s���ăC���X�g�[������Γ��������ł��B   

Win+Space�L�[��IME��؂�ւ��ē��͂����܂��B�ϊ�������������̍Ō�Ɂu�B�v�����ĕϊ����邱�ƂŁA�Ӗ�����ϊ����邱�Ƃ��ł��܂��B  

How to Build
-------
1.[OpenAI API key](https://platform.openai.com/api-keys)���擾���Ă��������B   
2.[Visual Studio 2022 Community Edition](https://visualstudio.microsoft.com/downloads/#visual-studio-community-2022)���C���X�g�[�����܂��B���̎��A�ȉ��̍��ڂ��C���X�g�[������悤�ɂ��Ă��������B  
- �uDesktop development with C++�v
- �uGit for Windows�v
- �uWindows11 SDK�v    

3.Python3(3.9�ȍ~)��Microsoft Store���ŃC���X�g�[�����Ă��������B    
4.Developer PowerShell for VS 2022���N�����Ă��������B����̃R�}���h�͂��ׂĂ����Ŏ��s���Ă��������B    
5.���̃��|�W�g�����N���[�����āAsrc�f�B���N�g���Ɉړ����܂��B    
```
git clone https://github.com/Team-Hmm/Hizk.git
cd mozc\src
```
6.[src\converter\segments.h](src/converter/segments.h)��1�s��`YOUR_API_KEY`�̕������A1.�Ŏ擾����API�L�[�ɏ��������܂��B
7.�ȉ��̃R�}���h�����s���āA�ǉ��̃c�[��([Ninja 1.11.0](https://github.com/ninja-build/ninja/releases/download/v1.11.0/ninja-win.zip)�E[Qt 6.6.2](https://download.qt.io/archive/qt/6.6/6.6.2/submodules/qtbase-everywhere-src-6.6.2.tar.xz)�E[WiX 3.14](https://github.com/wixtoolset/wix3/releases/download/wix314rtm/wix314-binaries.zip)�E[git submodules](../.gitmodules))����肵�܂��B
```
python -m pip install six requests
python build_tools/update_deps.py
```
8.�r���h�V�X�e���̃Z�b�g�A�b�v���s�����߂Ɉȉ��̃R�}���h�����s���܂��B
```
"C:\Program Files\Microsoft Visual Studio\2022\Community\VC\Auxiliary\Build\vcvarsamd64_x86.bat"
```
9.Qt��Hizk�̃r���h���ȉ��̃R�}���h�ōs���܂��B
```
python build_mozc.py gyp
python build_mozc.py build -c Release package
```
10.�ȉ��̃R�}���h�����s���邩�A`src\out_win\Release\Mozc64.msi`�����s���ăC���X�g�[�����܂��B
```
out_win\Release\Mozc64.msi
```

License
-------

All Hizk code written by Google & Team-Hmm is released under
[The BSD 3-Clause License](http://opensource.org/licenses/BSD-3-Clause).
For third party code under [src/third_party](src/third_party) directory,
see each sub directory to find the copyright notice.  Note also that
outside [src/third_party](src/third_party) following directories contain
third party code.

### [src/data/dictionary_oss/](src/data/dictionary_oss)
Mixed.
See [src/data/dictionary_oss/README.txt](src/data/dictionary_oss/README.txt)

### [src/data/test/dictionary/](src/data/test/dictionary)
The same to [src/data/dictionary_oss/](src/data/dictionary_oss).
See [src/data/dictionary_oss/README.txt](src/data/dictionary_oss/README.txt)

### [src/data/test/stress_test/](src/data/test/stress_test)
Public Domain.  See the comment in
[src/data/test/stress_test/sentences.txt](src/data/test/stress_test/sentences.txt)

### [src/data/unicode/](src/data/unicode)
UNICODE, INC. LICENSE AGREEMENT.
See each file header for details.
