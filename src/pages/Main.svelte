<script>
  import Header from "../components/Header.svelte";
  import Nav from "../components/Nav.svelte";
  import { getDatabase, ref, onValue } from "firebase/database";
  import { onMount } from "svelte";


  $: items = [];

  const calcTime = (timestamp) => {
  // 한국시간 UTC+9
        const curTime = new Date().getTime() - 9 * 60 * 60 * 1000;
        const time = new Date(curTime - timestamp);
        const hour = time.getHours();
        const minute = time.getMinutes();
        const second = time.getSeconds();

        if (hour > 0) return `${hour}시간 전`;
        else if (minute > 0) return `${minute}분 전`;
        else if (second > 0) return `${second}초 전`;
        else return "방금 전";
};

    const db = getDatabase();
    const itemsRef = ref(db, 'items/');

        onMount(()=>
        onValue(itemsRef, (snapshot) => {
        const data = snapshot.val();
        items = Object.values(data).reverse()
        }
        )
    );
   
</script>

<div class="media-info-msg">화면사이즈를 줄여주세요</div>
    <Header/>
    <!-- 메인 -->
    <a class="btn-write" href="#/write">+ 글쓰기</a>
    <main>
        {#each items as item}
            <div class="items-list">
                <div class="items-list__img">
                    <img alt={item.title} src={item.imgUrl}/>
                </div>
                <div class="items-list__info">
                    <div class="items-list__info-title">{item.title}</div>
                    <div class="items-list__info-meta">{item.place} {calcTime(item.insertAt)}</div>
                    <div class="items-list__info-price">{item.price}</div>
                    <!-- <div>{item.description}</div> -->
                </div>
            </div>
        {/each}
    </main>
    <Nav location='home'/>