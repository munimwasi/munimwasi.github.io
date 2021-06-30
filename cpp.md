---
layout: about
title: Sublime Build for C++
date: 2021-06-30 22:38:17 +0600
description: Submile Text
permalink: /sublimebuildcpp/
img: i-rest.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Sublime, C++]
---
```javascript
{
	"shell_cmd": "g++ -DLOCAL -std=c++17 -Wshadow -Wall -Wconversion -Wfatal-errors -fsanitize=address,undefined -D_GLIBCXX_DEBUG -g \"${file}\" -o \"${file_path}/${file_base_name}\"",
	"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
	"working_dir": "${file_path}",
	"selector": "source.c++",

	"variants":
	[
		{
			"name": "Slow All",
			"shell_cmd": "g++ -DLOCAL -std=c++17 -Wall -Wextra -pedantic -O2 -Wshadow -Wformat=2 -Wfloat-equal -Wconversion -Wlogical-op -Wshift-overflow=2 -Wduplicated-cond -Wcast-qual -Wcast-align -D_GLIBCXX_DEBUG -D_GLIBCXX_DEBUG_PEDANTIC -D_FORTIFY_SOURCE=2 -fsanitize=address -fsanitize=undefined -fno-sanitize-recover -fstack-protector -g \"${file}\" -o \"${file_path}/${file_base_name}\" && \"${file_path}/${file_base_name}\" <in1.txt >out1.txt && \"${file_path}/${file_base_name}\" <in2.txt >out2.txt && \"${file_path}/${file_base_name}\" <in3.txt >out3.txt"
		},
		{
			"name": "Fast All",
			"shell_cmd": "g++ -DLOCAL -std=c++17 -g \"${file}\" -o \"${file_path}/${file_base_name}\" && \"${file_path}/${file_base_name}\" <in1.txt >out1.txt && \"${file_path}/${file_base_name}\" <in2.txt >out2.txt && \"${file_path}/${file_base_name}\" <in3.txt >out3.txt"
		},
		{
			"name": "Slow Single (Terminal)",
			"shell_cmd": "g++ -DLOCAL -std=c++17 -Wall -Wextra -pedantic -O2 -Wshadow -Wformat=2 -Wfloat-equal -Wconversion -Wlogical-op -Wshift-overflow=2 -Wduplicated-cond -Wcast-qual -Wcast-align -D_GLIBCXX_DEBUG -D_GLIBCXX_DEBUG_PEDANTIC -D_FORTIFY_SOURCE=2 -fsanitize=address -fsanitize=undefined -fno-sanitize-recover -fstack-protector -g \"${file}\" -o \"${file_path}/${file_base_name}\" &&  mate-terminal -- /bin/bash -c 'time \"${file_path}/${file_base_name}\" <in1.txt; echo Press ENTER to continue...; read line'"
		},
		{
			"name": "Fast Single (Terminal)",
			"shell_cmd": "g++ -DLOCAL -std=c++17 -g \"${file}\" -o \"${file_path}/${file_base_name}\" &&  mate-terminal -- /bin/bash -c 'time \"${file_path}/${file_base_name}\" <in1.txt; echo Press ENTER to continue...; read line'"
		}
	]
}
```
