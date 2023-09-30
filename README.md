<!--- Banner -->
<br />
<p align="center">
<a href="#"><img src="https://i.ibb.co/fXpNrGq/image.png"></a>
<h3 align="center">Handcrafted Backdoors in Deep Neural Networks</h3>
<p align="center">Introducing backdoors in neural networks through parameter-level manipulation.</p>

<!--- About --><br />
## About

This project is a replication of the ["Handcrafted Backdoors in Deep Neural Networks
"](https://arxiv.org/abs/2106.04690) paper, which introduces a new form of white-box backdoor attack that directly manipulates a model's weights rather than relying on data poisoning. This implementation focuses on replicating these results on the MNIST dataset.

<!--- Backdoors --><br />
## Backdoors
<a href="#"><img src="https://i.ibb.co/2vtFjVG/image.png"></a>
Traditional backdoor attacks in machine learning usually rely on data poisoning. In this scenario, an attacker has access to the training data and subtly manipulates it to embed triggers. These triggers then activate malicious behavior in the trained model. In this approach however, we focus on the scenario where an attacker has access to a trained model, without the ability to tamper with the dataset or the training process.

<!--- How it works --><br />
## How it works
The backdooring method in question is designed to overcome four significant challenges: maintaining model accuracy, circumventing backdoor removal techniques, avoiding detection, and disguising backdoor signatures.

The approach starts with the observation that some neurons in a neural network are activated by important and easily interpretable patterns, such as facial features or specific objects. In contrast, other neurons respond to what appear to be random or unimportant patterns. In a typical, benign model, these neurons don't significantly affect the model's final output.

This method capitalizes on these under-utilized neurons by creating a new pathway in the neural network. This pathway routes through these particular neurons and is designed to only activate when a specific, pre-defined trigger is present in the input. This enables targeted misclassification without severely degrading the model's overall performance.

This method also takes additional steps to disguise these neural changes, making sure they are not easily identifiable through a simple parameter inspection or removable through conventional defensive strategies like fine-tuning or noise addition.
