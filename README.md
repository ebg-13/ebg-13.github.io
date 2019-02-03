# ROT13
ROT13 ("rotație de 13 poziții", câteodată scris ca și ROT-13) este o metodă simplă de codificare folosită în special, acum ceva timp, pe forum-urile online pentru a masca spoilere, glume, soluțiile unui puzzle, precum și materiale ofensatoare. ROT13 a fost descris ca și "Echivalentul pe internet a revistelor care imprimă răspunsul la întrebări intors". ROT13 este un exemplu de Cifru Cezar folosit în Roma antică. [Vezi mai mult](https://ro.wikipedia.org/wiki/ROT13).


![](https://upload.wikimedia.org/wikipedia/commons/thumb/3/33/ROT13_table_with_example.svg/320px-ROT13_table_with_example.svg.png)

## Cum să folosești convertorul
Pentru a folosi convertorul, trebuie să accesezi [această pagină](https://ebg-13.github.io). Poți introduce în caseta de text atât un text direct, scris în orice limbă, cât și un text în ROT13. Rezultatul va apărea pe pagina respectivă.

### ! ROT13 nu criptează textul
Să folosești ROT13 pentru a ascunde ceva este aproape ca și cum ai scrie un text invers, adică ɐșɐ. Nu este greu să descifrezi un text scris în ROT13, și, oricine poate folosi un convertor online pentru a afla, și textele ROT13 se pot descifra chiar în minte, fără niciun convertor.

### Ebg-13
**[Ebg-13](https://ebg-13.github.io)** este forma textului „Rot-13” scrisă chiar în ROT13, și, în același timp, numele convertorului. Convertirea textului introdus se face prin javascript, cu următorul cod simplu:

```javascript function rot13(c) {
	let offset = 0;

	let charCodeNumber = c.charCodeAt();

	if (charCodeNumber >= 97 && charCodeNumber <= 122) offset = 97;
	if (charCodeNumber >= 65 && charCodeNumber <= 90) offset = 65;

	if (offset) {
		return String.fromCharCode(((charCodeNumber - offset + 13) % 26) + offset);
	}
	return c;
}

$(document).ready(function () {
	$('#decrypted').on("input", function () {
		$('#encrypted').text(this.value.split('').map(function (element) {
			return rot13(element);
		}).join(''))
	});
});
