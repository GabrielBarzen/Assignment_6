
<script setup>
    let props = defineProps(["title", "grade"]);
    
    function remove(e) {
        let confirmed = confirm('Are you sure?');
        if (confirmed) e.target.parentElement.parentElement.parentElement.remove();

    }

    // let gradeStars = document.createElement("span");
    // let star = document.createElement("img");
    // star.src = "./icons/star.png"

    // for (let i = 0; i < props.grade; i++) {
    //     gradeStars.appendChild(star);
    // }

    // document.getElementById("grades").innerHTML = gradeStars;
    // console.log(props.grade);
</script>

<template>
    <li>
        <div>
            <span>
                {{title}}
            </span>
            <span id="grades">
                {{ grade }}
            </span>
            <span>
                <img src="./icons/delete.png" @click="remove"/>
            </span>
        </div>
    </li>
</template>
