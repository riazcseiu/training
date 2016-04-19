# ��2�� Opteron�̕��������_���j�b�g

- 2.1 ���������_�̃��l�[�����W�X�^�t�@�C��
- 2.2 ���������_���l�[���X�e�[�W1 : x87�̃X�^�b�N������FP���W�X�^�t�@�C���ւ̃}�b�s���O
- 2.3 ���������_���l�[���X�e�[�W2 : �ʏ�̃��W�X�^���l�[�~���O
- 2.4 ���������_���߃X�P�W���[��
- 2.5 5�|�[�g�ǂݍ��݂�5�|�[�g�������݂̕��������_���l�[�����W�X�^�t�@�C��
- 2.6 ���������_���Z���j�b�g
- 2.7 �ϊ��ƕ��ރ��j�b�g
- 2.8 x87��ԏ��� : FCOMI/FCMOV �� FCOM/FSTSW�y�A

![Opteron's Floating Point Processing Unit's](Opteron_FloatPnt_Core.jpg)

# 2.1 ���������_�̃��l�[�����W�X�^�t�@�C��

Opteron�̕��������_���l�[�����W�X�^�t�@�C���́A88����120�G���g���ɑ������Ă���B
���̃��l�[�����W�X�^�t�@�C���͌��t�ʂ�̈Ӗ��̃��W�X�^�t�@�C���ł���B
�P��̃G���e�B�e�B�������Ă���A���ׂẴA�[�L�e�N�`���I��(�񓊋@�I��)�l�ƁA���߃Z�b�g�ɂ���`���ꂽ���W�X�^�̓��@�I�Ȓl��ێ����Ă���B

Opteron�͍ēx72�̓��@�I�Ȗ��߂��i�[���邱�Ƃ��ł���B
AthlonXP�R�A�ɂ��A���@�I�Ȗ��߂̃T�|�[�g��72���߂���56���߂ɍ팸���ꂽ�B
AthlonXP�ł�SSE�̂��߂�128��XMM���W�X�^�t�@�C�����܂܂�Ă��邪�A88�̃��l�[�����W�X�^�t�@�C���̐��������邱�Ƃ͂Ȃ������B

128bit��XMM���W�X�^�̓��l�[�����W�X�^�t�@�C������2�̃G���g�����g�p����B
����������Opteron��16��XMM�A�[�L�e�N�`��(���^�C�A����)���W�X�^��ێ����邽�߂�32�G���g���𗘗p����B
����ɂ��A88+32�G���g����120�G���g���ƂȂ�B

120�G���g���̂���40�G���g���̓A�[�L�e�N�`����(�񓊋@�I��)���W�X�^�̏�Ԃ�ێ����邽�߂Ɏg�p�����B
32�G���g����16��XMM���W�X�^�p�ł���B�c���8��8��x87/MMX���W�X�^�p�ł���B

�����8�̃��W�X�^�G���g�����A�}�C�N���R�[�h�̃X�N���b�`���W�X�^�Ƃ��Ďg�p����B
����͎��X�}�C�N���A�[�L�e�N�`�����W�X�^�ƌĂ΂��B
�����̃��W�X�^�͖��߃Z�b�g�Ƃ��Ă͒�`����Ă��炸�A�v���O���}����͒��ڌ��邱�Ƃ͂ł��Ȃ��B
�����̃��W�X�^�̓}�C�N���R�[�h���A�O�p�֐���ΐ��֐��Ȃǂ̕��G�Ȍv�Z���s�����߂ɗ��p�����B

48(40+8)�G���g���ɂ���`�����v���Z�b�T�̃A�[�L�e�N�`���I�ȏ�Ԃ́A�u�A�[�L�e�N�`���^�O�A���C(Architectural Tag Array)�v
�Ƃ��Ē�`����Ă���B
���̃G���g���́A48�̃A�[�L�e�N�`���I�ȃ��W�X�^�G���g���̍ŐV�́u���@�I�ȁv�l��ێ����Ă���A�u�t���[�`���[�t�@�C���^�O�A���C
(Future File Tag Array)�v�ƌĂ΂��B

�v���Z�b�T�̓��@�I�ȏ�Ԃ́A����\�����O�̔����ɂ��������邱�Ƃ�����B
����̓t���[�`���[�t�@�C����48�G���g�����A�[�L�e�N�`���^�O�A���C�ŏ㏑�����邱�ƂŎ��������B

���l�[�����W�X�^�t�@�C����90bit���ł���B
���������_�̃f�[�^�͑S�̂�90bit�܂Ŋg�������(68bit�Ɖ������A18�r�b�g�̎w�����A1�r�b�g�̕����r�b�g�A3�r�b�g�̕��ރr�b�g�ł���)�B
3�̕��ރr�b�g�ς́A���������_���̏�񂪕t�������B
���̕��ރr�b�g�́A�񕂓������_��(����)�ȂǁA���l�[�����W�X�^�t�@�C���ɏ������ލۂɊg������K�v�̂Ȃ��l�����ʂ���Ƃ��Ȃǂɗ��p�����B

|    | The 120 registers                  |   |    | The 90 bit registers              |   |   | Definition of the 3bit Class Code  |
|----|------------------------------------|---|----|-----------------------------------|---|---|------------------------------------|
|    | non speculative registers:         |   |    | subdivision of the 90 bits for FP |   | 0 | Zero                               |
| 8  | FP/MMX registers(arch.)            |   | 68 | Mantisse bits                     |   | 1 | Inifinity                          |
| 32 | SSE/SSE2 registers(arch.)          |   | 18 | Exponent bits                     |   | 2 | Quit NAN (Not A Number)            |
| 8  | Micro Code Scratch Registers(arch) |   | 1  | Sign bit                          |   | 3 | Signaling NAN (Not A Number)       |
|    | speculative registers              |   | 3  | Class Code bits                   |   | 4 | Denormal (very small FP number)    |
| 8  | FP/MMX registers(latest)           |   |    |                                   |   | 5 | MMX/MMX (non FP contents)          |
| 32 | SSE/SSE2 registers(lates)          |   |    |                                   |   | 6 | Normal (FP number, not very small) |
| 8  | Micro Code Scratch reg.(latest)    |   |    |                                   |   | 7 | Unsupported                        |
| 24 | Renaming speculative               |   |    |                                   |   |   |                                    |

![Opteron's Floating Point Core](Opteron_FloatPnt_Core_Ill.jpg)

# 2.3 ���������_���l�[���X�e�[�W2 : �ʏ�̃��W�X�^���l�[�~���O

���ۂ̃��W�X�^���l�[�~���O�͂��̃X�e�[�W�Ŏ��s�����B
���̃X�e�[�W�ŁA�������ݐ惌�W�X�^���K�v�Ȗ��߂́A���l�[�����ꂽ���W�X�^���蓖�Ă��擾����B
�������݃��W�X�^�͎��s���̑��̂ǂ̂悤�Ȗ��߂Ƃ�����Ă��Ȃ���΂Ȃ�Ȃ��B
�h�̖��߂�����̃��W�X�^�ɏ������ނ��Ƃ͂Ȃ��̂ł���B
�t���[���X�g����́A�ő��3�̃��W�X�^�G���g�����擾���邱�Ƃ��ł���B
�S�̂ł�120�̃��W�X�^���g�p�\�ł���B
�t���[���X�g�́A�ő��72�̃t���[�G���g����ێ����邱�Ƃ��ł��A�ő�œ����Ɏ��s���ɂ��邱�Ƃ��ł��閽�߂̐��ɓ������B

���l�[�~���O���Ă���48�G���g���́A�A�[�L�e�N�`���I��(�񓊋@�I��)���W�X�^�̒l��ێ����Ă���:8��x87/MMX���W�X�^�ł���B
8�̃X�N���b�`���W�X�^(�}�C�N���R�[�h�ł̂݃A�N�Z�X�\)��SSE��SSE�Q�ŗ��p�����128bit��XMM���W�X�^�́A���ꂼ��2�G���g���g�p����B
�����̃��W�X�^�͏ꏊ���Œ肳��Ă���킯�ł͂Ȃ����A120�G���g���̂����ǂ����𗘗p���邱�ƂɂȂ�B
����ɂ��A�t���[���X�g���K�v�ɂȂ�킯�ł���B
48�G���g���́A��L�ɏq�ׂ��悤�ɁA48�́u�A�[�L�e�N�`���^�O�A���C�v�ɂ���Ď��ʂ��邽�߂̃A�[�L�e�N�`�����W�X�^�ɂ���ė��p�����B
�A�[�L�e�N�`���^�O�A���C�́A120�̃��l�[�����W�X�^����A�e�A�[�L�e�N�`�����W�X�^���x�̃G���g���Ƀ}�b�s���O����Ă��邩���������߂̃A���C�ł���B

1�T�C�N��������ő��3���߂����l�[�~���O���邱�Ƃ��ł���B
�f�[�^�ˑ��́A�u�t���[�`���[�t�@�C���^�O�A���C�v�Ƃ������̋@�\��p���ď��������B
���̃A���C�́A���@�I�Ȃ����l��ێ����Ă���48�̃��l�[�����W�X�^�ւ̃|�C���^��ێ����Ă���B
���߂̓��l�[�~���O���ꂽ���W�X�^�A�N�Z�X���s�����߂ɁA���̃A���C�ɃA�N�Z�X���邱�Ƃɂ��\�[�X�I�y�����h���擾���邱�Ƃ��ł���B
���߂̓t���[�`���[�^�O�A���C�ɁA���l�[�����ꂽ����z�u���A����ɂ��㑱�̖��߂͂��̖��߂̌��ʂ��i�[�����ꏊ��m�邱�Ƃ��ł���B

��: ���閽�߂��A�[�L�e�N�`�����W�X�^��3��5����̓I�y�����h�Ƃ��ė��p���A���W�X�^3���������ݐ�Ƃ��Ďg�p����B
�ŏ��ɃG���g��3��5��ǂ݁A���W�X�^3�ƃ��W�X�^5�̓��@�I�Ȓl���i�[����Ă��郊�l�[�����W�X�^�̃|�C���^���擾����B
���̃��l�[�����W�X�^�̏ꏊ��93��12�ł���Ƃ���B
���̖��߂͓��̓I�y�����h�̏ꏊ���擾�����̂ŁA�t���[�`���[�^�O�A���C�̃��W�X�^�ԍ�3�̈ʒu�Ɍ��ʂ��i�[����郊�l�[�����W�X�^�̃G���g���ԍ����������ށB
�����Ⴆ��97�Ƃ���B
�㑱�̖��߂ŁA���W�X�^�h����3���K�v�Ȗ��߂́A���l�[�����W�X�^97�𗘗p���ăA�N�Z�X���邱�ƂɂȂ�B

��O�╪��\���~�X�����������Ƃ��́A�t���[�`���[�^�O�A���C��48�G���g�����A�A�[�L�e�N�`���^�O�A���C��48�G���g���ŏ㏑������B
����ł��ׂĂ̓��@�I�Ɏ��s���ꂽ���߂͔j�������B
�A�[�L�e�N�`���^�O�A���C�̃|�C���^�̓��^�C�A�����̘_���ɂ���ď������܂��B
���^�C�A������1�T�C�N��������3�̒l���������ނ��Ƃ��ł���B
�����̒l�̓��I�[�_�o�b�t�@���狟�������B
���I�[�_�o�b�t�@�͂��ׂĂ̖��߂����L���Ă���B

���������_���߂́A���߂��I�������Ƃ��ɗ�O���̂悤�Ȃ������̏���ێ����Ă���ATOS�Ȃǂ��A���I�[�_�o�b�t�@�Ɋi�[����B
���̏��ɂ́A���̖��߂��ύX�����������ݐ�̃��W�X�^���Ȃǂ��܂܂�Ă���B
���I�[�_�o�b�t�@�ɂ̓A�[�L�e�N�`�����W�X�^�̔ԍ��ƃ��l�[�����W�X�^�̔ԍ����܂܂�Ă���B
�����̂���2���A���^�C�A�����̍ۂɃA�[�L�e�N�`���^�O�A���C�̍X�V�ɗ��p�����B
1�̓f�[�^�ł���A������̓A�[�L�e�N�`���^�O�A���C�̃G���g���ԍ��ł���B

