---
title: My Gallery
show_profile: true
images:
 - /portfolio/theme/img/gal1c.jpg
 - /portfolio/theme/img/gal2c.jpg
 - /portfolio/theme/img/gal1n.jpg
 - /portfolio/theme/img/gal3.jpg
 - /portfolio/theme/img/gal2n.jpg
 - /portfolio/theme/img/gal4c.png
 - /portfolio/theme/img/gal5c.png
 - /portfolio/theme/img/gal5n.png
---

<style>
 .h:hover{
  opacity: 0.5;
 } 
</style>

My collection of gallery.


<div class="card-columns">
    {% for img in page.images %}
    <div class="card w-75" data-toggle="modal" data-target="#exampleModal" data-img="{{ img }}">
        <img class="card-img-top h" src="{{ img }}" />
    </div>
    {% endfor %}
</div>

<div class="modal fade" id="exampleModal">
  <div class="modal-dialog modal-lg modal-dialog-centered">
    <div class="modal-content w-75">
      <div class="modal-header">
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
        <img class="modal-img w-100" />
      </div>
    </div>
  </div>
</div>

<script type="text/javascript">
  $(document).ready(function() {
    $('#exampleModal').on('show.bs.modal', function (event) {
      var button = $(event.relatedTarget)
      var img = button.data('img')
      var modal = $(this)
      modal.find('.modal-img').attr('src', img)
    })
  })
</script>
