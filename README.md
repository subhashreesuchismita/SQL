# SQL
CREATE TABLE authors (
    author_id INT PRIMARY KEY,
    author_name VARCHAR(100)
);

CREATE TABLE books (
    book_id INT PRIMARY KEY,
    title VARCHAR(255),
    author_id INT,
    available BOOLEAN,
    FOREIGN KEY (author_id) REFERENCES authors(author_id)
);

CREATE TABLE members (
    member_id INT PRIMARY KEY,
    member_name VARCHAR(100),
    phone_number VARCHAR(20)
);
INSERT INTO authors (author_id, author_name)
VALUES (1, 'John Doe'),
       (2, 'Jane Smith');

INSERT INTO books (book_id, title, author_id, available)
VALUES (101, 'Java Programming', 1, true),
       (102, 'Python Programming', 2, true);

INSERT INTO members (member_id, member_name, phone_number)
VALUES (1001, 'Alice Brown', '123-456-7890'),
       (1002, 'Bob Green', '987-654-3210');
       SELECT book_id, title, author_name
FROM books
JOIN authors ON books.author_id = authors.author_id
WHERE available = true;
SELECT book_id, title
FROM books
JOIN authors ON books.author_id = authors.author_id
WHERE authors.author_name = 'John Doe'
SELECT member_id, member_name, phone_number
FROM members;
UPDATE books
SET available = false
WHERE book_id = 101;
DELETE FROM members
WHERE member_id = 1002;
