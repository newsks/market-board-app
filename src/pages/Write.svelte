<script>
  import { getDatabase, ref, push } from "firebase/database";
  import { getStorage,ref as refImage, uploadBytes, getDownloadURL } from "firebase/storage";

  import Header from "../components/Header.svelte";
  import Nav from "../components/Nav.svelte";

    let title; 
    let price;
    let description;
    let place;
    let files;
    

    // 이미지 업로드

    const storage = getStorage();
    const db = getDatabase();


    async function writeUserData(imgUrl) {
        push(ref(db, 'items/'), {
            title,
            price,
            description,
            place,
            insertAt:new Date().getTime(),
            imgUrl,
        });
        alert('글쓰기가 완료되었습니다')
        window.location.hash="/"
    }

    const uploadFile= async ()=>{
      const file = files[0];
      const name = file.name;
      const imgRef = refImage(storage, name)
      await uploadBytes(imgRef, file)
      const url = await getDownloadURL(imgRef)
      return url
    }

    const handleSubmit =async ()=>{
      const url = await uploadFile();
      writeUserData(url)
    }
</script>

<Header/>
  <!-- 글쓰기 영역 -->
  <form id="write-from" on:submit|preventDefault ={handleSubmit}>
    
    <div class="write-list-img">
      <label for="image" class="write-title">이미지</label>
      <input type="file" bind:files id="image" name="image" class="write-input" />
    </div>
    <div class="write-list">
      <label for="title" class="write-title">제 목</label>
      <input type="text" id="title" name="title" class="write-input" bind:value={title} />
    </div>
    <div class="write-list">
      <label for="price" class="write-title">가 격</label>
      <input type="number" id="price" name="price" class="write-input" bind:value={price}/>
    </div>
    <div class="write-list">
      <label for="description" class="write-title">설 명</label>
      <input
        type="text"
        id="description"
        name="description"
        class="write-input"
        bind:value={description}
      />
    </div>
    <div class="write-list">
      <label for="place" class="write-title">장 소</label>
      <input type="text" id="place" name="place" class="write-input" bind:value={place}/>
    </div>
    <div>
      <button type="submit" class="btn-submit">글쓰기 완료</button>
    </div>
  </form>
  <Nav location='write'/>