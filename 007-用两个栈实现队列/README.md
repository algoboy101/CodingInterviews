#����
------- 

>ţ��OJ��[������ջʵ�ֶ���](http://www.nowcoder.com/practice/54275ddae22f475981afa2244dd448c6?tpId=13&tqId=11158&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-rankingg) 
>
>�Ŷ�OJ��http://ac.jobdu.com/problem.php?pid=1512
>
>GitHub���룺 [007-������ջʵ�ֶ���](https://github.com/gatieme/CodingInterviews/tree/master/006-%E9%87%8D%E5%BB%BA%E4%BA%8C%E5%8F%89%E6%A0%91)  
>
>CSDN��⣺[��ָOffer--007-������ջʵ�ֶ���](http://blog.csdn.net/gatieme/article/details/51112580)



| 牛客OJ | 九度OJ | CSDN题解 | GitHub代码 
|:-------:|:-------:|:-------:|:-------:|
|[������ջʵ�ֶ���](http://www.nowcoder.com/practice/54275ddae22f475981afa2244dd448c6?tpId=13&tqId=11158&rp=1&ru=/ta/coding-interviews&qru=/ta/coding-interviews/question-rankingg) | [1512-������ջʵ�ֶ���](http://ac.jobdu.com/problem.php?pid=1512)   | [��ָOffer--007-������ջʵ�ֶ���](http://blog.csdn.net/gatieme/article/details/51112580) | [006-�ؽ�������](https://github.com/gatieme/CodingInterviews/tree/master/006-%E9%87%8D%E5%BB%BA%E4%BA%8C%E5%8F%89%E6%A0%91)  |

<br>
**��Ҳ����ѡ��[�ص�Ŀ¼-��ָOffer--�⼯Ŀ¼����](http://blog.csdn.net/gatieme/article/details/51916802)**


#����
-------
��Ŀ����


>������ջ��ʵ��һ�����У���ɶ��е�Push��Pop������ �����е�Ԫ��Ϊint���͡�

#����
-------

ʼ��ά��s1��Ϊ**�洢�ռ�**����s2��Ϊ**��ʱ������**��

*    ���ʱ����Ԫ��ѹ��s1��

*    ����ʱ����s1��Ԫ����������롱��������ѹ�룩s2����s2�Ķ�Ԫ�ص�����Ϊ����Ԫ�أ�֮���ٽ�s2ʣ�µ�Ԫ����������ء�s1��

������ʾ��ͼ��

![������ջģ�����](./stack2queue.jpg)

����˼·����������ӹ���ɡ�����һ��ϸ���ǿ����Ż�һ�µġ������ڳ���ʱ����s1��Ԫ����������롱s2ʱ��ԭ��s1ջ�׵�Ԫ�أ����á����롱s2����ֻ������s1.Count()-1��������ֱ�ӵ�����Ϊ����Ԫ�ط��ء��������Լ���һ��ѹջ�Ĳ�����Լ��һ���ˣ�����ʾ������ʶ�������⡣
 
����˼·����Щ���֣��磺

*    ���ʱ�����ж�s1�Ƿ�Ϊ�գ��粻Ϊ�գ�˵������Ԫ�ض���s1����ʱ�����Ԫ��ֱ��ѹ��s1����Ϊ�գ�Ҫ��s2��Ԫ����������ء�s1����ѹ�����Ԫ�ء�

*    ����ʱ�����ж�s2�Ƿ�Ϊ�գ��粻Ϊ�գ�ֱ�ӵ���s2�Ķ�Ԫ�ز����ӣ���Ϊ�գ���s1��Ԫ����������롱s2�������һ��Ԫ�ص��������ӡ�
��Щ����ͬʱ�뵽���ڷ����ͱ��֣�Ӧ��˵ͷ�Ի��ǱȽ����ġ�
 
����ڵ�һ�ַ��������ֵ�s2����Ƚϡ�������ÿ�γ��Ӻ󣬲�����Ԫ�ء����ء�s1����������´λ��ǳ��Ӳ�����Ч�ʻ��һЩ�����´��������Ӳ�����Ч�ʲ����һ�ַ���������ʱ���������߷����Ƚϲ�ͬ���������ܡ��Ҹо���û�������о�������ӡ����Ӳ�������ֲ�ʱ���������ַ���������ʱ�临�ӶȺͿռ临�Ӷ�Ӧ������޼����޷Ƕ���ٸ��жϣ���
 
����ÿ�ε�����ȥ�Ļ���Ч�ʲ�̫�ã��������˼���������µı���

ʼ��ά��s1��Ϊ**����ջ**����s2��Ϊ**���ջ**

*    ���ʱ����Ԫ��ѹ��s1��

*    ����ʱ���ж�s2�Ƿ�Ϊ�գ��粻Ϊ�գ���ֱ�ӵ�����Ԫ�أ���Ϊ�գ���s1��Ԫ����������롱s2�������һ��Ԫ�ص��������ӡ�
���˼·�������˷���������ջ��������Ҫʱ�š�����һ�Ρ�����ʵ�������к�������˵����������ʱ����ٵ�Ե�ʰɡ�

#����
-------
```cpp
#include <iostream>
#include <stack>
using namespace std;

//  ���Կ���
#define __tmain main

#ifdef __tmain

#define debug cout

#else

#define debug 0 && cout

#endif // __tmain

class Solution
{
public:
    void push(int node)
    {
        stackIn.push(node);
    }

    int pop()
    {
        int node = -1;

        //  ����ջ����NULL��ʱ����������Ϊ��
        if(this->empty( ) == true)
        {
            debug <<"��������ΪNULL" <<endl;

            return -1;
        }
        else
        {
            //  �����������Ԫ��
            //  ��ʱ�����������
            //  �����ջ��Ϊ�յ�ʱ��, ֱ�ӽ����ջ��Ԫ�ص�������
            //  �����ջΪNULL, ��������ջ��Ϊ�յ�ʱ����Ҫ������ջ��Ԫ��ȫ���������ջ��

            if(stackOut.empty() == true)     //  ��ʱ���ջΪ��, ����ջ�ز�Ϊ��
            {
                //  ��ʱ����ջ�����ջ����û��Ԫ��
                //  ��Ҫ������ջ�е�Ԫ�ص������ջ
                // ������ջ����û��Ԫ��

                //  ����Ԫ�ش�����ջ�������ջ
                while(stackIn.empty( ) != true)
                {
                    node = stackIn.top( );
                    stackIn.pop( );
                    stackOut.push(node);
                    debug <<node <<"�������ջ" <<endl;
                }
            }

            node = stackOut.top( );
            stackOut.pop( );

            debug <<"��ͷԪ��" <<node <<endl;
        }

        return node;
    }

    bool empty( )
    {
        return (stackIn.empty() == true && stackOut.empty() == true);
    }

private:
    stack<int> stackIn;
    stack<int> stackOut;
};


int __tmain( )
{
    Solution solu;
    solu.push(1);
    solu.push(2);
    solu.push(3);
    solu.push(4);

    int node;
    while(solu.empty() != true)
    {

        cout <<solu.pop( );
    }

    return 0;
}

```
