
# ���y : <�]�p�Ҧ��P�C���}�o���������X> �պӤ��

<h1> Part 1.�]�p�Ҧ� && �C���]�p</h1>

<h2> Ch1.�C����@�����]�p�Ҧ� </h2>

<h3> Ch1-2.�]�p�Ҧ��O����? </h3>

�ѨM�@�A�X�{�����D�A"�Ҧ�"=�ѨM���=SOP

<h3> Ch1-3.�`�����]�p��h </h3>

�`��:

�E��@¾�d��h (SRP: Single Responsibility Principle)�G
��]�p�@�����O�ɡA�����O���ӥu�t�d�@��¾�d�Υ\��C
�Ҧp�A�@�� User ���O���ӥu�t�d�B�z�ϥΪ̪���ơA�Ӥ����ӦP�ɭt�d�B�z��Ʈw�s���εo�e�l�󵥥\��C

�E�}��ʳ���h (OCP: Open-Closed Principle)�G
�n�����]���O�B�ҲաB�禡���^���ӹ��X�R�}��A��ק������A�z�L�����Ω�H�ƨӹ�{�C
���]���@�� Shape ��H���O�A�����@�� draw() ��k�C�{�b�ڭ̭n�s�W�@�ӷs���Ϊ� Triangle�A�ڭ̥i�H�~�� Shape �ù�@ draw() ��k�Hø�s�T���ΡA�Ӥ��ݭn�ק�쥻�� Shape ���O�C


�E������N��h (LSP: Liskov Substitution Principle)�G
�l���O����������������O�A�Ӥ��|�}�a�즳�{�������T�ʡC
�p�G���@�Ӥ����O Animal�A�����@�� makeSound() ��k�C
�l���O�p Dog �� Cat ���ӥi�H���N�����O Animal�A�Ӥ��v�T�쥻���{���޿�C�Ҧp�ADog �M Cat ���i�H��@�ۤv�� makeSound() ��k�A�����M�i�H�Q���� Animal �����N�~�C


�E�̿�ʤϦV��h (DIP: Dependency Inversion Principle)�G
1.���h�Ҳդ����Ө̿��C�h�ҲաA��̳����Ө̿���H�����Φ@�P����H�h�šC
2.��H���������Ө̿���@�Ӹ`�A��@�Ӹ`���Ө̿���H�����C
���]���@�Ӱ��h�Ҳ� NotificationManager �t�d�B�z�q�����o�e�A���̿���H�� NotificationService �����A�Ӥ��O���骺��@�C
���骺�q���A�Ȧp EmailNotificationService �� SMSNotificationService �|��@ NotificationService �����A�M��Q�`�J�� NotificationManager ���C


�E�������έ�h (ISP: Interface Segregation Principle)�G
�Ȥ�ݤ����ӳQ���ϥΤ��ݭn��������k�C�������ӲӤ����S�w¾�d�Ψϥγ������p�������C
���]���@�� FileManager ���O�A����@�F readFile() �M writeFile() ��Ӥ�k�C
�p�G�Y�ӫȤ�ݥu�ݭn�ϥ� readFile() ��k�A�h�����ӳQ����@�ΨϥΤ��ݭn�� writeFile() ��k�C
�i�H�N FileManager ���\����Φ���Ӥ����A���O�O Readable �M Writable�A���Ȥ�ݥu��@�ݭn�������C


�E�̤֪��ѭ�h (LKP: Least Knowledge Principle)�G
�@�����O���Ө�Ƴ̤֪����ѡA�u�M�������������O���ʡA������O���������X�סC
�p�G�@�����O�ݭn�P��L�h�����O�i�椬�ʡA�̦n�����k�O�ȻP�������������O�i�椬�ʡA������O�������̿����Y�C
�Ҧp�A�@�� Order ���O�����Ӫ����P PaymentGateway �i�椬�ʡA�����өe�����@�� PaymentProcessor ���O�B�z��I�������ާ@�A�q�ӭ��C�F Order ���O����I�t�Ϊ����ѩM�̿�C

�E�֨ϥ��~�ӡA�h�ϥβզX�O�@�ر`�����]�p��h�A�٬�"�u���ϥβզX�]Favor Composition Over Inheritance�^"
1.�קK���O��������K���X�A�����F���ʩM�i���@�ʡC
2.�����N�X���iŪ�ʡA���C�����ʡC
3.��n���u�ʩM�X�i�ʡC
4.�P�i�N�X���ΡC
�d�ҡG
���]�ڭ̥��b�}�o�@�ӹC���A�����P����������A�p�Ԥh�]Warrior�^�M�k�v�]Mage�^�C�o�Ǩ��ⳣ���@�Ǧ@�P���ݩʩM�欰�A�Ҧp�W�r�]Name�^�M�����]Attack�^�C
�ǲΪ��]�p��k�i��O�Ыؤ@�Ӥ����O Character�A�M�����Ԥh�M�k�v�z�L�~�Ө���o�@�P���ݩʩM��k�C�M�ӡA�ϥ��~�ӥi��|���ͽ����ʩM���X�ת����D�C
�ۤϡA�ڭ̥i�H�ϥβզX�ӹ�{�o�ӻݨD�C�����A�Ыؤ@�� Character ���O�A���]�t�@�P���ݩʩM�欰�A�Ҧp�W�r�M�����C�M��A���O�Ы� Warrior �M Mage ���O�A���̤��O�֦��W�S���ݩʩM��k�C
�b�C�����O���A�N Character ����@�������ܼƲզX�i�ӡC�o�ˤ@�ӡA�C�Ө������O�i�H�ϥ� Character ����ӳX�ݦ@�P���ݩʩM�欰�A�P�ɮھڦۤv���S�ʨӹ�{�B�~���欰�C

<h3> Ch1-4.������n�ǳ]�p�Ҧ� </h3>

�ǲߥ��H���z
�������s��ҷs���ѨM���
�Q���ҹL���Ҧ�

<h3> Ch1-6. </h3>

�T�j��:
�ͦ��Ҧ� (Creational):���ͪ��󪺹L�{�Τ覡
���c�Ҧ� (Structural):���O�Ϊ��󤧥�զX���覡
�欰�Ҧ� (Behavioral):���O�Ϊ��󤧶����ʩάO�d�����t���覡

<h1> Part 2-��¦�t��</h1>

<h3> Ch3.�C�������ഫ - State ���A�Ҧ� </h3>

7/17



: ���@�Ӫ��󪺦欰�H�ۤ������A�����ܦ��ܤơA�ӸӪ���]�����F���O�@�ˡC

�EGameLoop
�C���D�j��

�ESceneStateController 
�������A����� 

�EISceneState
����

�EStartState �BMainMenuState�BBattleState
���� �}�l�����B�D�e�������B �԰�����


<h3> Ch4.�C���D�n���O - Facade �~�[�Ҧ� </h3>






<h1> Part 3.���⪺�]�p</h1>
<h1> Part 4.���⪺����</h1>
<h1> Part 5.�Ԫ��}�l</h1>
<h1> Part 6.���U�t��</h1>
<h1> Part 7.�վ�P�̨Τ�</h1>
<h1> Part 8.�����T�ϥΪ��Ҧ�</h1>

