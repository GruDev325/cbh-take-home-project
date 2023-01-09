# Refactoring

You've been asked to refactor the function `deterministicPartitionKey` in [`dpk.js`](dpk.js) to make it easier to read and understand without changing its functionality. For this task, you should:

1. Write unit tests to cover the existing functionality and ensure that your refactor doesn't break it. We typically use `jest`, but if you have another library you prefer, feel free to use it.
2. Refactor the function to be as "clean" and "readable" as possible. There are many valid ways to define those words - use your own personal definitions, but be prepared to defend them. Note that we do like to use the latest JS language features when applicable.
3. Write up a brief (~1 paragraph) explanation of why you made the choices you did and why specifically your version is more "readable" than the original.

You will be graded on the exhaustiveness and quality of your unit tests, the depth of your refactor, and the level of insight into your thought process provided by the written explanation.

## Your Explanation Here
1. I added all possisble test cases in case of having no param, object param with partitionKey, object param with different keynames, partitionKey length bigger than 256 etc.
2. Original code had unnessessary if statements. We need evaluate event param has value or not, after that we need to check event param is object or not, if yes we can check if it has partitionKey key. We only have the case of partitionKey length bigger than Max partition key length when the event param is object and partionKey key. Here original codebase duplicated the evaluation process. That reduces the performance of the function.

3.I added comments on the refactored codebase dpk.js
