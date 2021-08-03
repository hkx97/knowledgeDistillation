# 知识蒸馏（分类）
## step1.训练教师网络(保存权重)
## step2.截取teacher经softmax之前的输出，作为soft-output，计算soft-loss（和student的output之间的KL散度）
## step3.计算hard-loss（student-output和真实label）
## step4.Loss = lambda*soft-loss+(1-lambda)*hard-loss
$$
loss = \alpha CE(q, \tilde q) + (1-\alpha) CE(p, q)
$$


p为真实标签，q为学生网络输出（经过softmax）， $\tilde q$ 为老师网络输出（不经过softmax）再经过softmaxT

前部分称为soft loss（KL），后部分称为hard loss（cross—entrophy）

![](http://consolexinhun.test.upcdn.net/20200523181929.png)
