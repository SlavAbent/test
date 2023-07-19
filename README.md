# 1. Какой из двух фрагментов кода не сработает и почему?

 Сработает фрагмент кода 2 так как имеет больший приоритет в компиляторе js - определяется функция, тогда как в первом фрагменте кода сначала определяется переменная dublenum = undefined и только потом в нее присваивается функция - функциональное выражение.

# 2. Исправьте ошибку в фрагменте коде так, чтобы после компиляции в шаблоне не было лишних тегов

К сожалению со Vue мало работал, специализируюсь в основном на react-стеке, но могу предположить, что необнодимо сделать так, как сказано в документации:

перенести из component-name в template v-for="i o count" и :key="i"


# 3. 

resources = [
    {
        id: 1,
        count: 13,
    },
    {
        id: 2,
        count: 5,
    },
    {
        id: 3,
        count: 24,
    },
    {
        id: 4,
        count: 101,
    },
    {
        id: 5,
        count: 72,
    },
    {
        id: 6,
        count: 64,
    },
    {
        id: 7,
        count: 305,
    },
    {
        id: 8,
        count: 67,
    },
    {
        id: 9,
        count: 95,
    },
    {
        id: 10,
        count: 21,
    },
    {
        id: 11,
        count: 37,
    },
];

// => { "id":"count" }

3.1
const reformatData = resources.map(({id, count}) => [id, String(count)])

const result = Object.fromEntries(reformatData)
console.log(result)

3.2
const result = resources.reduce((acc, cur) => (acc[cur.id] = String(cur.count), acc), {})

console.log(result)

3.3
let obj = {};

for (let i = 0; i < resources.length; i++) {
    obj[resources[i]['id']] = String(resources[i]['count']);
}

console.dir(obj);
