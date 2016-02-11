---
title: Online Prayers
layout: default
id: shyambaba
---
<script src="//cdnjs.cloudflare.com/ajax/libs/jquery-timeago/1.4.1/jquery.timeago.min.js"></script>

<h3 id="post-msg"></h3>
<form id="post-form" action="https://a.kishan.info/comments/?id={{ page.id }}" method="post">
<label for="name">Name</label><br>
<input type="text" id="name" name="name" style="width:50%" required><br>
<label for="msg">Message</label><br>
<textarea id="msg" name="msg" rows="8" style="width:50%" required></textarea><br>
<input type="text" name="foo" style="display:none">
<button type="submit">Post</button>
</form>

<br>

<div id="comments"><noscript>Not </noscript>Loading...<noscript> (Please enable JavaScript or use a different browser to view this page.)</noscript></div>
<script>
$('#comments').load('https://a.kishan.info/comments/{{ page.id }}.htm', function() {
    $('time').timeago().each(function(){
        $(this).attr('title', new Date($(this).attr('datetime')).toString().replace(/ GMT.*/,''));
    });
});

$('#post-form').submit(function(event){
    $('#post-msg').text('Posting...');
    $.post( $('#post-form').attr('action'), $('#post-form').serialize(), function(res) {
        $('#post-msg').text(res);
        $('#msg').text('');
    }, 'text' );
    event.preventDefault();
});
</script>
