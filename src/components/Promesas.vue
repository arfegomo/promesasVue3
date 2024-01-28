<script setup>
    const datos = [{
        id: 1,
        title: 'Iron Man',
        year: 2008
    },
    {
        id: 2,
        title: 'Spirdeman: Homecoming',
        year: 2017
    },
    {
        id: 3,
        title: 'Avengers: Endgame',
        year: 2019
    }];

    //const datos = [];

    //Example Promise
    const getDatos = () => {
        return new Promise((resolve, reject) => {
            if(datos.length === 0){
                reject(new Error('There are not data'));
            }
            setTimeout(() => {
                resolve(datos);
            }, 1500);
        })
    }

    //console.log(getDatos());
    
    //Forma # 1 Promise
    getDatos().then((data) => console.log(data));

    //Forma # 2 async - await
    const fetchingData = async () => {
        try {
            const dataFetched = await getDatos();
            console.log(dataFetched);    
        } catch (error) {
            console.log(error.message);
        }
        
    }

    fetchingData();     




</script>

<template>
    <h1>Promesas</h1>
</template>

<style scoped>

</style>