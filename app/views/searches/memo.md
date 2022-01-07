<div class='container px-5 px-sm-0'>
  <h1>Books search for "" %></h1>
  <table class="table　table-hover table-inverse">
    <% if @range == "User" %>
      <thead>
        <tr>
          <th>image</th>
          <th>name</th>
        </tr>
      </thead>
      <tbody>
        <% @users.each do |user| %>
          <tr>
            <th><%= attachment_image_tag(user, :profile_image, :fill, 50, 50, fallback: "no-image-icon.jpg") %></th>
            <th><%= user.name %></th>
          </tr>
        <% end %>
      </tbody>
    <% else %>
      <thead>
        <tr>
          <th></th>
          <th>title</th>
          <th>body</th>
        </tr>
      </thead>
      <tbody>
        <% @books.each do |book| %>
          <tr>
            <th>%= book.title %></th>
            <th><%= book.text %></th>
          </tr>
        <% end %>
      </tbody>
    <% end %>
  </table>
</div>
