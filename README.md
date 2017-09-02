# Least Privilege JavaScript Modules

> If chrome-privileged code is compromised, the attacker can take over the user's computer.

[Mozilla's X-ray doc (retrieved Sept 2nd 2017)](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/Xray_vision)

This is also the case in Node.js: if a single module gets compromised, the attacker can `require` `fs` or `net` and do whatever.

This situation is ridiculous. The origins and solutions to this problem are well-known:
- https://www.youtube.com/watch?v=UH66YrzT-_M
- https://www.youtube.com/watch?v=eL5o4PFuxTY
- https://www.youtube.com/watch?v=vrbmMPlCp3U
- https://www.youtube.com/watch?v=w9hHHvhZ_HY

Most chrome-privileged code in Firefox does not **need** the authority to take over the user's computer and as a 
consequence **should not have access** to it.

Most Node.js modules do not need access to all the APIs, and as a consequence should not have access to it.

This repo is used to discuss/work on a mecanism to drastically reduce the privileges provided by default to a given module

## Goals

- Reduce privilege by default
- Ease of use
- Neutral against JS runtimes
- Can be used without the need of official distribution (npm)
- Explicitly say which module gets which authority it gets
- Declarative mechanism. (Dynamic mechanisms already exist: passing an argument to a function)


## Precedent

Apps in iOS, Android and Chrome/WebExtension extensions require the author to declare which authority they want ahead of time. 
If an application tries to use more privilege than what is declared, an error is thrown (well, at least in browser extensions).



