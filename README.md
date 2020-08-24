# DB-Competencies

1. DB - Patterns (one-one)

Solutions: 

SELECT * FROM album
WHERE title LIKE ('%Wall%')

SELECT * FROM album
WHERE title LIKE ('%Wall%') OR title LIKE '%a'


2.  Patterns (many-many)

Solutions:

SELECT * FROM album
WHERE (title LIKE '%Bee%'
       OR title LIKE '%Moon%'
       OR title LIKE '%Of%')
     
       
SELECT * FROM album
WHERE title ~ '(Dance | Office | Best)'



3. DB - Statements (sub-queries)


Solutions: 

SELECT * FROM artist
WHERE artist_id IN (SELECT artist_id FROM album WHERE title ~ '(Great | Loud)')

SELECT * FROM track
WHERE name LIKE '%Rock You%' AND album_id IN (SELECT album_id FROM album WHERE artist_id IN (SELECT artist_id FROM artist))
