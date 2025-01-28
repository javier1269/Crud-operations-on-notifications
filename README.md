CREATE TABLE notifications (
    notification_id SERIAL PRIMARY KEY,
    user_id INT NOT NULL REFERENCES users(user_id),
    message TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    is_read BOOLEAN DEFAULT FALSE
);

INSERT INTO notifications (user_id, message) 
VALUES (5, 'Your aid request has been approved.')

SELECT * FROM notifications WHERE user_id = 1 AND is_read = FALSE;

UPDATE notifications 
SET is_read = TRUE 
WHERE notification_id = 1;

DELETE FROM notifications WHERE notification_id = 1;

SELECT * FROM public.notifications
ORDER BY notification_id ASC 
