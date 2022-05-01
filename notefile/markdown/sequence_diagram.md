支持的箭头
-> 		Solid line without arrow
--> 	Dotted line without arrow
->>		Solid line with arrowhead
-->>	Dotted line with arrowhead
-x		Solid line with a cross at the end
--x		Dotted line with a cross at the end.
-)		Solid line with an open arrow at the end (async)
--)		Dotted line with a open arrow at the end (async)

Participants （可使用别名as）
```mermaid
sequenceDiagram
	participant Alice
	participant J as John
	Alice->>J: Hello John, how are you?
	J-->>Alice: Great!
	Alice-)J: See you later!
```

关联 （可使用+/-号简化）
```mermaid
sequenceDiagram
	Alice->>John: Hello John, how are you?
	activate John
	John-->>Alice: Great!
	deactivate John
	Alice->>+John: Hello John, how are you?
	John-->>-Alice: Great!
```

可叠加
```mermaid
sequenceDiagram
	Alice->>+John: Hello John, how are you?
	Alice->>+John: John, can you hear me?
	John-->>-Alice: Hi Alice, I can hear you!
	John-->>-Alice: I feel great!
```

边注 （可跨越）
```mermaid
sequenceDiagram
	Alice->>John: Hello John, how are you?
	Note left of Alice: Text left
	Note right of Alice: Text right
	Note over John: Text join
	Note over Alice,John: Text cross
```

块：
```mermaid
sequenceDiagram
	loop Every minute
		Alice->>John: Hello John, how are you?
		John-->>Alice: Great!
	end
```

```mermaid
sequenceDiagram
	Alice->>Bob: Hello Bob, how are you?
	alt is sick
		Bob->>Alice: Not so good :(
	else is well
		Bob->>Alice: Feeling fresh like a daisy
	end
	opt Extra response
		Bob->>Alice: Thanks for asking
	end
```

```mermaid
sequenceDiagram
	par Alice to Bob
		Alice->>Bob: Hello guys!
	and Alice to John
		Alice->>John: Hello guys!
	end
	Bob-->>Alice: Hi Alice!
	John-->>Alice: Hi Alice!
```

```mermaid
sequenceDiagram
	par Alice to Bob
		Alice->>Bob: Go help John
	and Alice to John
		Alice->>John: I want this done today
		par John to Charlie
			John->>Charlie: Can we do this today?
		and John to Diana
			John->>Diana: Can you help us today?
		end
	end
```

序号：
```mermaid
sequenceDiagram
	autonumber
	Alice->>John: Hello John, how are you?
	loop Healthcheck
		John->>John: Fight against hypochondria
	end
	Note right of John: Rational thoughts!
	John-->>Alice: Great!
	John->>Bob: How about you?
	Bob-->>John: Jolly good!
```
