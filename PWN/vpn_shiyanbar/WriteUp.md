# vpn writeup

---
1. 对程序进行反汇编，在主函数中并未发现可能的溢出风险。但是注意到下图红框内函数可能存在问题。

    ![](./Resource/fig.1.png '描述')

2. 进入该函数后发现，由于下图红框处输入验证码的代码存在漏洞，因此导致下图蓝框处的p指针会被b数组覆盖。

    ![](./Resource/fig.2.png '')

3. 因此考虑通过溢出将p指针覆盖，由题目知是美国地区的VPN，因此找到了下图红框所示的函数，只需修改p指针跳转至此即可。

    ![](./Resource/fig.3.png '')

4. 由于4016CC(H)=4200140(O)，因此进行下图的操作即可获得flag。其中第四个数只是用来占位，并无特殊意义。

    ![](./Resource/fig.4.png '')