### Enum Integration

#### Tag Row

```ruby
show do
  attributes_table do
    # another attributes...
    tag_row :state
  end
end
```

<img src="./images/enumerize-tag-row-example.png" height="200" />

#### Tag Column

```ruby
index do
  # another attributes...
  tag_column :state
end
```

<img src="./images/enumerize-tag-column-example.png" height="150" />

If you want to customize the tag's colors. You need to define css classes matching enumerize attribute values. For example: if you have the `Bill` model with:

```ruby
class Bill < ActiveRecord::Base
  # Enumerize
  extend Enumerize
  enumerize :state, in: [:rejected, :approved]

  # Rails Enum
  enum status: { active: 0, archived: 1 }

end
```

You will need to define inside `your_app/app/assets/stylesheets/active_admin.css.scss` the following:

```scss
.status_tag {
  &.rejected { background: $rejected-color; }
  &.approved { background: $approved-color; }
}
```
