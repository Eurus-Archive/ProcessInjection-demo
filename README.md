# Process Injection Learning Repository

This repository contains code and resources for learning about Process Injection and related security topics. 
It is based on materials from a YouTube channel and is meant for educational purposes.



## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Topics Covered](#topics-covered)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This repository serves as a learning resource for those interested in understanding the concept of Process Injection, a common technique used in cybersecurity and malware analysis. 
The materials provided here are inspired by the content available on Channel: [@crr0ww](https://www.youtube.com/@crr0ww) and Link: [Malware Development](https://www.youtube.com/watch?v=aNEqC-U5tHM&list=PL_z_ep2nxC57sHAlCcvvaYRrpdMIQXri1)

## Getting Started

To get started with this repository, follow these steps:

1. Clone the repository to your local machine:
   ```sh
   git clone https://github.com/yourusername/process-injection-learning.git
   ```

## Topics Covered

### CreateRemoteThread vs. CreateThread
CreateRemoteThread �� CreateThread ���� Windows ����ϵͳ�ṩ�����ڴ����̵߳ĺ�����������֮����һЩ��Ҫ������

ʹ�ó���:

CreateThread: ͨ�����ڴ��������̣߳�Ҳ�����ڵ�ǰ�����ڴ����µ��̡߳�
CreateRemoteThread: ��Ҫ���ڴ���Զ���̣߳�Ҳ���������������ڴ����µ��̡߳���ͨ������ע����뵽���������У�ִ��Զ���߳���ʵ��ĳЩ�ض����ܣ���DLLע������ע�롣
����:

CreateThread: �����̺߳����ĵ�ַ��Ϊ��������������������߳���ִ�С����������̵߳���ʼ��ջ��С���̱߳�־�Ȳ�����
CreateRemoteThread: �����̺߳�����ַ֮�⣬����Ҫָ��Ŀ����̵ľ���Լ��̺߳����Ĳ�����
Ȩ��:

CreateThread: ������ͬһ�����ڴ����̣߳����Ե��ý���ͨ�������㹻��Ȩ���������̡߳�
CreateRemoteThread: ����Զ���߳���Ҫ��Ŀ����̾����㹻��Ȩ�ޣ�ͨ����Ҫ����ԱȨ�޻�DebugȨ�ޣ���Ϊ���漰�����������̵ĵ�ַ�ռ���ִ�д��롣
������:

CreateThread: �ڴ���ʧ��ʱ������ֱ��ͨ����������ֵ�� GetLastError ��ȡ������Ϣ��
CreateRemoteThread: �ڴ���Զ���߳�ʧ��ʱ��ͨ����Ҫͨ�� WriteProcessMemory ������Զ�̲��������ݴ�����Ϣ��Ŀ����̣���ͨ��Ŀ������ڵķ�������ȡ������Ϣ��
�̵߳Ĺر�:

CreateThread: �������߳�ͨ���븸������ֹʱ�Զ��رա�
CreateRemoteThread: ������Զ���߳�ͨ����Ŀ�������ֹʱ�Զ��رգ�����Ҫע���ڸ������д����쳣����Ա���Ŀ����̱�����
��֮��CreateThread �����ڱ��ؽ����д����̣߳��� CreateRemoteThread ���������������д����̣߳�ͨ������ʵ�ֽ���ע�롢����ע��ȸ��ӵĲ�����ʹ������������ʱ��Ҫע��Ȩ�ޡ���������̵߳��������ڵȷ���Ĳ��졣

### VirtualAllocEx �е�LPVOID����������
`VirtualAllocEx` ������������Ŀ����̵������ַ�ռ��з����ڴ�ĺ�����������Զ�̽����ڴ����ڴ�顣`VirtualAllocEx` �����Ĳ�������һ�� `LPVOID` ���͵Ĳ�������ʾҪ������ڴ����ʼ��ַ��

�����ǹ��� `VirtualAllocEx` ������ `LPVOID` ���������ú���;�Ľ��ͣ�

1. **�����ڴ�λ��**��`LPVOID` ����ָ����Ҫ��Ŀ������ڷ����ڴ�����ʼ��ַ������Խ������������Ϊ�����ĵ�ַ������ʹ���ض���ֵ���� `NULL`������ϵͳ�Զ�ѡ���ʵ��ĵ�ַ��

2. **�ڴ汣������**��`VirtualAllocEx` ��������������ָ��������ڴ��ı������ԣ�����ɶ�����д����ִ�еȡ���Щ���Կ����� `flProtect` ������ָ����������ڴ�齫���ݱ������Խ��з������ơ�

3. **�ڴ���С**��`VirtualAllocEx` ͨ�����ڷ���һ���ض���С���ڴ档������� `dwSize` ������ָ��Ҫ������ڴ��Ĵ�С��

4. **����ֵ**��`VirtualAllocEx` �����ķ���ֵ�Ƿ�����ڴ�����ʼ��ַ��������� `LPVOID` ������ָ����һ������ĵ�ַ�������������ڸõ�ַ�������ڴ档����������Ŀ����̵ĵ�ַ�ռ���Ѱ�ҿ��õĵ�ַ�������ط�����ڴ���ʵ����ʼ��ַ��

��֮��`LPVOID` ������ `VirtualAllocEx` ����������ָ��Ҫ�����ڴ����ʼ��ַ��������������������Ŀ������ڷ����ڴ��λ�ã��Լ�������ڴ��Ĵ�С�ͷ������ԡ���������������ȷ���������������ȷ���ڴ������Զ�̽������������С�