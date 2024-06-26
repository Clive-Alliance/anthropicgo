# anthropicgo

# <span>Anthropicgo: Anthropic LLM API Client for golang

## What

The goal of this library is to provide an easy, scalable, and hassle-free way to build LLM-driven application using Anthropic API in golang applications. It is built on the following principles:

1. Fidelity to the original Anthropic API response and behavioural implementations: the aim is to accurately provide LLM integrations mirrioring Anthropic inference speed and golang super capabilities, so that Large Language Models can be implemented seamlessly and deployed in golang applications
2. Hassle-free and performant production use

## For whom

For the golang developer or AI/ML engineer who wants to run Anthropic LLMs on their own Agentic/RAG/ChatBot, tightly coupled with their own application.
It is blazing FAST; try it and see! 🏎️ 💨 💨 💨

## Installation and usage

To use Anthropicgo, you need to obtain an API key from https://console.anthropic.com/settings/keys and create your .env key as:

ANTHROPIC_API_KEY="sk_xxxxxxxxxxxxxxxxxxxxxxxx"

```go
go get github.com/clive-alliance/anthropicgo
```


```go
package main

import (
	"fmt"
	"github.com/clive-alliance/anthropicgo"
)

func LLM() (*anthropicgo.AnthChatArgs){

	kwargs := []map[string]interface{}{{
		"model": "llama3-8b-8192",
		"temperature":0.2,
		"max_tokens": 5048,
		"stream": true,
		"stop":[]string{"Observation"},
	}}

	llm := anthropicgo.ChatAnth(kwargs...)
	
	return llm
}


func main() {
	llm,_ := LLM()
	systemPrompt := "You are an AI assistant who excels at making comical statements just like Kevin Hart"
	userPrompt := "Define the concept of AI?"
	res,_:=llm.Chat(userPrompt,systemPrompt)
    if err != nil {
			fmt.Print(err.Error())
		}
	fmt.Print(res)
}

```

## Contributing

### Contribution process

1. create or find an issue for your contribution
2. fork and develop
3. add tests and make sure the full test suite passes and test coverage does not dip below 80%
4. create a MR linking to the relevant issue

### Run the tests

The full test suite can be run as follows.

```go

go test

```
Thank you for contributing to groqgo!