# restful-blog-microservices-phase3

This project is part of the transformation to microservices of project https://github.com/benjsicam/restful-blog, it was splitted in 4 stages for educational purposes

Take into account that for this stage you have to  complete all stage 2, for this stage you will need to create three new databases with the following tables:

**restful_blog_categories**
```sql
CREATE TABLE IF NOT EXISTS `category` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `name` varchar(50) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8;

INSERT INTO `category` (`id`, `name`) VALUES
	(1, 'General'),
	(2, 'News'),
	(3, 'Announcements');

CREATE TABLE IF NOT EXISTS `post_category` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `post_id` bigint(20) NOT NULL,
  `category_id` bigint(20) NOT NULL,
  PRIMARY KEY (`id`),
  KEY `FK4BC509BD1CD41CA0` (`category_id`),
  CONSTRAINT `FKqly0d5oc4npxdig2fjfoshhxg` FOREIGN KEY (`category_id`) REFERENCES `category` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=utf8;

INSERT INTO `post_category` (`id`, `post_id`, `category_id`) VALUES
	(1, 1, 1),
	(2, 4, 1),
	(3, 2, 2),
	(4, 5, 2),
	(5, 3, 3),
	(6, 6, 3); 
```


Also you will need to setup include a new file in git repository for the spring cloud configurtion service, if you are using windows you can use gitstack free version. The repository was named  restful_blog_configuration_properties, that is category.properties
