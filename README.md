# API Installation

1. Clone repository:
   ```bash
   git clone https://github.com/adibminanurohman/Apitest-Laravel11-SantriKoding.git
   ```

2. Install dependencies:
   ```bash
   composer install
   ```

3. Edit `.env` file:
   ```
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=db_laravel11_api
   DB_USERNAME=root
   DB_PASSWORD=
   ```

4. Generate application key:
   ```bash
   php artisan key:generate
   ```

# API Documentation

## Base URL
```
http://api-berita.test/api
```

## Endpoints

### Get All Posts
**Endpoint:** `GET /posts`

- **Description:** Retrieve a list of all posts.
- **URL:** `http://api-berita.test/api/posts`
- **Method:** `GET`
- **Response:**
  ```json
  [
    {
      "id": 1,
      "title": "Post Title",
      "content": "Post content",
      "image": "URL to image",
      "created_at": "2024-07-18T00:00:00.000000Z",
      "updated_at": "2024-07-18T00:00:00.000000Z"
    },
    ...
  ]
  ```

### Create a New Post
**Endpoint:** `POST /posts`

- **Description:** Create a new post.
- **URL:** `http://api-berita.test/api/posts`
- **Method:** `POST`
- **Request Body:**
  - `image` (file): The image file to upload.
  - `title` (text): The title of the post.
  - `content` (text): The content of the post.
- **Example Request Body (form-data):**
  ```
  key: image, type: file, value: {insert file img}
  key: title, type: text, value: {insert text}
  key: content, type: text, value: {insert text}
  ```
- **Response:**
  ```json
  {
    "id": 1,
    "title": "Post Title",
    "content": "Post content",
    "image": "URL to image",
    "created_at": "2024-07-18T00:00:00.000000Z",
    "updated_at": "2024-07-18T00:00:00.000000Z"
  }
  ```

### Update a Post
**Endpoint:** `PUT /posts/{id}`

- **Description:** Update an existing post.
- **URL:** `http://api-berita.test/api/posts/{id}`
- **Method:** `PUT`
- **Request Body:**
  - `image` (file): The image file to upload (optional).
  - `title` (text): The title of the post.
  - `content` (text): The content of the post.
- **Example Request Body (form-data):**
  ```
  key: image, type: file, value: {insert file img}
  key: title, type: text, value: {insert text}
  key: content, type: text, value: {insert text}
  ```
- **Response:**
  ```json
  {
    "id": 1,
    "title": "Updated Post Title",
    "content": "Updated post content",
    "image": "URL to updated image",
    "created_at": "2024-07-18T00:00:00.000000Z",
    "updated_at": "2024-07-18T00:00:00.000000Z"
  }
  ```

### Delete a Post
**Endpoint:** `DELETE /posts/{id}`

- **Description:** Delete a specific post.
- **URL:** `http://api-berita.test/api/posts/{id}`
- **Method:** `DELETE`
- **Response:**
  ```json
  {
    "message": "Post deleted successfully"
  }
  ```
```