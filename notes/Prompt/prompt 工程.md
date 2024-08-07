# prompt 工程

## Principles of Prompting

#### Write clear and specific instructions

1、Use Delimiters

特殊符号引导语料部分，确保模型可以分开提示词和语料。

提示冲突：用户在自己的输入部分，写了和开发者相互冲突的指令，通过特殊符号的分割，确保模型可以将用户的内容只作为语料

2、Ask for structured output

结构化输出，可以要求HTML或json

提示模型的输出结构，可以输出的内容结构更加清晰

3、Check whether conditions are satisfied, Check assumptionos required to do the task

对你的目标文本做一定的限制，例如指令或者故事，并对不满足的情况做指定输出，防止意外

4、Few-shot prompting

提供一个成功的案例，然后后续的任务做同样的事情

#### Give the model time to think

1、Specify the steps to completa a task

将任务分解为一个小步骤，随后对每一步的输出做格式要求，保证输出的稳定

2 、Instruct the model to work out its own solution before rushing  to a conclusion

在直接用大模型做判断之前，可以先让大模型自己做出一个解决方案，通过大模型的方案对比和实际的区别来判断，效果会比直接让大模型做判断要准确

#### Model Limitations

Hallucination

幻觉，模型可能会因为问题，虚构一个不存在的东西（要求中不是要虚构）

Reducing hallucinations

1、找到关联文档，并基于这些关联文档回答

## Iterative Prompt Development

![Untitled](prompt%20%E5%B7%A5%E7%A8%8B/Untitled.png)

Prompt guidelines

Be clear and specific

Analyze why result does not give desired output

Refine the idea and the prompt

Repeat

<aside>
💡 chips:

use words, sentences or characters to control the length of output

</aside>

Iterative Process

Try something

Analyze where the result does not give what you want

Clarify instructions, give more time to think

Refine prompts with a batch of examples

## Summarizing

这部分在给出对应的prompt的时候，可以通过改变文本的需求对象，来改变总结的侧重点

extract提取信息，会比总结文本更加干练

可以通过循环的方式，对多个文本进行分次总结

## Inferring

1、提取文本的情绪导向，通过调整输出形式。

可以只输出positive

可以输出happy,satifised,greatful

可以对特定情绪做判断

2、提取文本关键词头信息，例如文本中强调的主体对象。

3、提取文本的核心几个主题。

4、反向根据几个主题，判断文本是否和这几段文本有关（新事件提醒）

## Transforming

校对文本，文本翻译，根据身份转写，书面和非书面，语气转换

类型转换（口头语到商业信件），格式转化（json-html）

拼写检查、语法检查

## Expanding

eg：根据客户的评论的情感和你内容，生成对应的回复邮件

Temperature（模型随机性）（是不是只会选择概率最大的选项，稳定性的表现）

通过更改temperature参数，对同样的问题得到不同的回答。

## Chatbots

system层面对AI做一个人设限制，由此后续的回答都会基于此

设定一个流程，和相关的信息，可以由此得到一个符合任务需求的问答机器人