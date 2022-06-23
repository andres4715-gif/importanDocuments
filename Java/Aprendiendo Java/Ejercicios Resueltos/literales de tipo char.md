# Ejercicio sobre literales de tipo char

[here](http://puntocomnoesunlenguaje.blogspot.com/2020/12/ejercicio-sobre-literales-de-tipo-char.html) para mas información

Indica cuáles de los siguientes literales de tipo char son válidos en Java. Si el literal no es válido explica el motivo.

1.  'a'
2.  '$'
3.  '\n'
4.  '/n'
5.  '\\'
6.  '\ñ'
7.  "T"
8.  'ñ'
9.  'xyz'
10. '\u0066'
11. "XYZ"
12. '4'
13. '\t'
14. '\b'
15. k
16. -
17. '+'
18. '?'
19. 'â'
20. ':'

Solución:

LITERAL VÁLIDO

---

1. 'a' SI

---

2. '$' SI

---

3. '\n' SI Es una secuencia de escape

---

4. '/n' NO No válido. Un literal de tipo carácter debe estar formado por un
   solo carácter a no ser que sea una secuencia de escape.

---

5. '\\' SI Es una secuencia de escape

---

6. '\ñ' NO Un literal de tipo carácter debe estar formado por un solo
   carácter a no ser que sea una secuencia de escape.

---

7. "T" NO Los literales de tipo carácter deben ir entre comillas simples.

---

8. 'ñ' SI

---

9. 'xyz' NO Un literal de tipo carácter debe estar formado por un solo
   carácter a no ser que sea una secuencia de escape.

---

10. '\u0066' SI Representa un valor Unicode.

---

11. "XYZ" NO Los literales de tipo carácter están formados por un solo
    carácter y deben ir entre comillas simples.

---

12. '4' SI

---

13. '\t' SI Es una secuencia de escape

---

14. '\b' SI Es una secuencia de escape

---

15. k NO Los literales de tipo char deben inr entre comillas simples.

---

16. -               NO   Los literales de tipo char deben inr entre comillas simples.

---

17. '+' SI

---

18. '?' SI

---

19. 'â' SI

---

20. ':' SI

---
