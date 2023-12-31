# Симметричная криптография

## Введение

В настоящее время все существующие криптосистемы принято разделять на два класса: _симметричные_ и _асимметричные_.

Соответственно, говорят о симметричной криптографии и асимметричной криптографии.

__В симметричных криптосистемах__ одним и тем же секретным ключом осуществляется и шифрование, и расшифрование:

$$E_k(P) = C,
D_k(C) = P$$

где $Е$ – функция зашифрования, $k$ – ключ, $P$ – открытый текст, $С$ – шифртекст,
$D$ – функция расшифрования.

При этом справедливо следующее равенство:
$D_k(E_k(P)) = P$

### Потоковые и блочные шифры

Алгоритмы, которые обрабатывают открытый текст побитово (побайтово), называют __потоковыми алгоритмами__ или потоковыми шифрами.

Алгоритмы, которые обрабатывают группы битов (блоки) открытого текста, называют __блочными алгоритмами__ или блочными шифрами.

Долгое время в компьютерных алгоритмах типичный размер блока был равен 64 битам. Это достаточно большое значение, чтобы затруднить анализ, и в то же время достаточно малое, чтобы быть удобным для работы. В настоящее время используются 128-разрядные блоки, так как длина блока в 64 бита не удовлетворяет современным требованиям эффективности и надежности алгоритмов.

Наиболее широко применяемыми на практике симметричными криптосистемами долгое время являлись системы DES (стандарт США), IDEA (европейский стандарт), ГОСТ (стандарт РФ) и их модификации.

## Блочные шифры

### Принцип построения

Пусть шифруемое сообщение представлено в виде последовательности нулей и единиц. Если перед шифрованием эта последовательность
разбивается на блоки фиксированной длины 𝑛 и затем каждый блок
шифруется отдельно, то такое шифрование называется __блочным__.

![Блочное шифрование](images/image.png)

Каждый блок принято называть _открытым текстом_ (plaintext) и обозначать через $𝑃$. Размер блока, как правило, составляет несколько десятков битов (например, 64, 128, 256 бит). _Ключом_ (key) $𝐾$ называется секретная последовательность битов длины $𝑚$, используемая при шифровании некоторого (достаточно большого) числа блоков. Современными длинами ключей являются, например, 128, 256, 512 бит. Блочный шифр состоит из нескольких _раундов_, на каждом из которых происходит обратимое преобразование блока длины $𝑛$ в новый блок той же длины. Выходной блок $𝑖$-го раунда называется _промежуточным шифртекстом_ и обозначается $𝐶_𝑖$. Он является входным блоком следующего $𝑖 + 1$-го раунда. Входным блоком первого раунда служит $𝐶_0 = 𝑃$. _Шифртекстом_ (ciphertext) $𝐶$ называется выходной блок последнего раунда, $𝐶 = 𝐶_𝑟$. Число раундов $𝑟$ (на практике, от 8 до 64) должно быть, с одной стороны, достаточно большим для обеспечения высокой криптостойкости шифра, а с другой стороны, достаточно малым для того, чтобы шифрование было быстрым. Часто на всех раундах шифра используется одно и то же преобразование зависящее лишь от разных битов ключа. А именно из ключа формируется $𝑟$_подключей_$𝐾_1, . . . , 𝐾_𝑟$, каждый из которых используется на
определенном раунде.

### Примеры блочных шифров

#### DES/3DES

DES осуществляет шифрование блоков длины 64 бита. Длина ключа составляет 56 бит. Число раундов равно 16. Последовательно приведем способ выбора раундовых ключей, общую схему шифрования DES и непосредственно саму раундовую функцию.

##### Раундовые ключи

Будем считать, что в каждом блоке биты нумеруются слева направо, начиная с первого бита. Ключ $𝐾$ обычно представляют блоком длины 64 бита, в котором каждый восьмой бит зависимый — он равен сумме по модулю 2 предыдущих семи битов плюс 1 (такие зависимые биты называются проверками на четность). На подготовительном этапе из ключа $𝐾$ формируются 16 подключей $𝐾_1, . . . , 𝐾_{16}$ длины 48. А именно сначала по ключу $𝐾$ строятся блоки $𝐶_0$ и $𝐷_0$, состоящие каждый из 28 битов:
![Блоки](images/blocks.png)
Например, первый бит блока $𝐶_0$ — это 57-й бит ключа $𝐾$, второй бит — 49-й бит ключа и т. д. слева направо и сверху вниз. Аналогично, первым битом блока $𝐷_0$ является 63-й бит ключа $𝐾$ и т. д. Обратим внимание, что в блоки $𝐶_0$ и $𝐷_0$ не входят зависимые биты ключа, т. е. биты с номерами 8, 16, 24, 32, 40, 48, 56 и 64. Далее, начиная с блоков $𝐶_0$ и $𝐷_0$, индуктивно строятся блоки $𝐶_𝑖$ и $𝐷_𝑖$, где $𝑖 = 1,...,16$.Блоки $𝐶_𝑖$ и $𝐷_𝑖$ получаются из блоков $𝐶_{𝑖−1}$ и $𝐷_{𝑖−1}$ их циклическим сдвигом влево на один или два бита в зависимости от индекса $𝑖$:

#### AES

_текст_

#### Kuznechik

_текст_

#### RC4

_текст_

#### RC5

_текст_
