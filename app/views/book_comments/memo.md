<div>
<%= form_with(model:[@book, @book_comment], local: true) do |f| %>
  <div class="form-group">
    <%= f.text_area :comment,　rows:'5', class: 'form-control book_comment_comment' %>
  </div>
  <div class="form-group">
    <%= f.submit "送信" %>
  </div>
<% end %>
</div>

<% @book.book_comments.each do |book_comment| %>
  <tr>
    <td>
    <%= attachment_image_tag(book_comment.user, :profile_image, :fill, 50, 50, fallback: "no-image-icon.jpg") %><br>
    <%= book_comment.user.name %>
    </td>
    <td>
    <%= book_comment.comment %>
    <% if book_comment.user == current_user %>
    <%= link_to 'Destroy', book_book_comment_path(book_comment.book, book_comment), method: :delete, class: "btn btn-sm btn-danger destroy_book" %>
    <% end %>
    </td>
  </tr>
<% end %>