---
layout: layouts/index.njk
title: Blog Post
---

<link rel="stylesheet" href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
		integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T"
		crossorigin="anonymous">



<div class="input-group ">
<textarea id="content" class="form-control" placeholder="Enter the content" rows="5"></textarea>
</div>
<div>
<button type="button" id="btn" class="btn btn-primary float-right my-3">Submit</button>
</div>
<div class="input-group">
<div id="posted"></div>
</div>

<script>
    let desc = document.getElementById("content");
    let button = document.querySelector("#btn");
    
    showPost();

    button.addEventListener("click",()=>{
    let posts = localStorage.getItem("content");
    if(posts == null){
        newPost = [];
    }
    else {
        newPost = JSON.parse(posts);
    }
    newPost.push(desc.value);
    localStorage.setItem("content", JSON.stringify(newPost));
    desc.value = "";
    showPost();
    })


    function showPost(){
    let posts = localStorage.getItem("content");
    if (posts == null){
    newPost = [];
    }
    else {
     newPost = JSON.parse(posts);
    }
    let html = "";
  
    newPost.forEach(function(element, index) {
        let cutIt = element.substring(0, 200);
        html += `<div class="card m-3">
                     <div class="card-body m-3">
                       <h5 class="card-title">
                        Post ${index + 1}
                    </h5>
                    <div id="edit" class="card-text"> 
                        <div>${cutIt}....<a href="/post/" class="card-link">Read More</a></div>
                    </div>
                     <button id="${index}" onClick="deletePosts(this.id)"
                    class="btn btn-info">
                    Delete Post
                </button>
                </div>
               </div>`
    })
    let addPost = document.getElementById("posted")
    if (newPost.length != 0) {
        addPost.innerHTML = html;
    }
    else{
        addPost.innerHTML = `Nothing to show! Type your article`;
    }
    }
    
    function deletePosts(index){
    let confirmDel = confirm("Are you sure you want to delete this post?");
    if(!confirmDel) return;

    let posts = localStorage.getItem("content");
    
    if (posts == null) newPost = [];
	
    else newPost = JSON.parse(posts);
  
    newPost.splice(index, 1);
  
    localStorage.setItem("content", JSON.stringify(newPost));
  
    showPost();
    }
    
    
</script>
