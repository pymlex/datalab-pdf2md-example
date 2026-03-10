# PDF2MD Datalab Marker Example

<img width="338" height="200" alt="image" src="https://github.com/user-attachments/assets/71e182d4-373e-4cb4-b9b6-ae697a8c94b3" />

A Colab-ready notebook demonstrating how to convert PDF books into high-quality Markdown suitable for LLM pipelines. The notebook uses `marker` (Datalab) to convert PDFs to Markdown with LaTeX rendering, image processing, and structured JSON metadata.

## Functional abilities

* Convert PDF collections to Markdown with LaTeX formulas rendered.
* Produce paired outputs: `.md` (text) and `.json` (formatting metadata).
* Suitable output for RAG pipelines and fine-tuning preparation.

---

## Notes on performance & result

Tested on 5 textbook volumes, OCR-read, with LaTeX. Typical Colab T4 throughput observed: ~0.15–0.21 pages/sec for 300-page documents with `--workers 3`. Each input produces an `.md` file and a `.json` metadata file. Output Markdown preserves LaTeX formulas and is ready for tokenisation / indexing.

---

## Example snippet

4.15. Атом массы  $m_1$  испытал неупругое столкновение с покоившейся молекулой массы  $m_2$ . После соударения обе частицы разлетелись под углом  $\vartheta$  друг к другу с кинетическими энергиями  $K_1'$  и  $K_2'$  соответственно, причем молекула оказалась в возбужденном состоянии — ее внутренняя энергия увеличилась на определенную величину Q. Найти Q, а также пороговую кинетическую энергию атома, при которой возможен переход молекулы в данное возбужденное состояние.

Р е ш е н и е. Из законов сохранения энергии и импульса в этом процессе следует:

$$\begin{split} K_1 &= K_1' + K_2' + Q, \\ p_1^2 &= {p_1'}^2 + {p_2'}^2 + 2\,p_1'\,p_2'\cos\,\vartheta, \end{split}$$

где штрихами отмечены величины после соударения (второе соотношение сразу следует из треугольника импульсов согласно теореме косинусов). Воспользовавшись формулой  $p^2=2mK$ , исключим  $K_1$  из этих уравнений. В результате получим

$$Q = (m_2/m_1 - 1)K_2' + 2\sqrt{(m_2/m_1)K_1'K_2'\cos\vartheta},$$
 
$$K_{1\text{nop}} = |Q|(m_1 + m_2)/m_2.$$
