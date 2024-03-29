======== Database tables ===========

1. Yashodha Amarasinghe

-- Table structure for table `food_categories`

CREATE TABLE `food_categories` (
  `categoryId` int NOT NULL,
  `categoryName` varchar(100) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

ALTER TABLE `food_categories`
  ADD PRIMARY KEY (`categoryId`);

-- Table structure for table `food_items`

CREATE TABLE `food_items` (
  `itemId` int NOT NULL,
  `categoryId` int NOT NULL,
  `image` varchar(255) NOT NULL,
  `itemName` varchar(100) NOT NULL,
  `itemDescription` varchar(200) NOT NULL,
  `unitPrice` double NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

ALTER TABLE `food_items`
  ADD PRIMARY KEY (`itemId`);

ALTER TABLE `food_items`
  ADD CONSTRAINT `catergory_id` FOREIGN KEY (`categoryId`) REFERENCES `food_categories` (`categoryId`) ON DELETE CASCADE ON UPDATE CASCADE;

-- Table structure for table `oderDetails`

CREATE TABLE `order_details` (
  `orderNo` int NOT NULL,
  `itemName` varchar(100) NOT NULL,
  `itemId` int NOT NULL,
  `quantity` int NOT NULL,
  `unitPrice` int NOT NULL,
  `totalUnitPrice` int NOT NULL,
  `orderStatus` varchar(50) NOT NULL,
  `memberId` int NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

ALTER TABLE `orderDetails`
  ADD PRIMARY KEY (`orderNo`);

2. Mayuri Yashodha

-- Table structure for table `user_ registration`

CREATE TABLE `user_ registration` (
  `member_id` int NOT NULL,
  `first_name` varchar(50) NOT NULL,
  `last_name` varchar(50) NOT NULL,
  `contact_number` int NOT NULL,
  `e_mail` varchar(20) NOT NULL,
  `address` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL,
  `send_offers` tinyint(1) NOT NULL,
  `user_name` varchar(20) NOT NULL,
  `password` varchar(20) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

-- Table structure for table `table_reservation`

CREATE TABLE `table_reservation` (
  `reservation_id` int NOT NULL,
  `member_id` int NOT NULL,
  `name` varchar(50) NOT NULL,
  `contact_number` int NOT NULL,
  `booking_date` date NOT NULL,
  `reservation_date` date NOT NULL,
  `number_of_guests` int NOT NULL,
  `check_in_time` time(5) NOT NULL,
  `check_out_time` time(5) NOT NULL,
  `preferable view` varchar(50) NOT NULL,
  `special_arrangements` varchar(100) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;


3. Udashi Jayaneththi

-- Table structure for table `event_booking`

CREATE TABLE `event_booking` (
  `event_id` int NOT NULL,
  `member_id` int NOT NULL,
  `first_name` varchar(50) NOT NULL,
  `last_name` varchar(50) NOT NULL,
  `phone_number` varchar(50) NOT NULL,
  `email` varchar(100) NOT NULL,
  `select_room` varchar(50) NOT NULL,
  `number_of_guest` int NOT NULL,
  `event_date` date NOT NULL,
  `start_time` time NOT NULL,
  `end_time` time NOT NULL,
  `menu_style` varchar(50) NOT NULL,
  `event_status` tinyint(1) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

ALTER TABLE `event_booking`
  ADD PRIMARY KEY (`event_id`);

-- Table structure for table `delivery`

CREATE TABLE `delivery` (
  `delivery_id` int NOT NULL,
  `oder_id` int NOT NULL,
  `delivery_address` varchar(100) NOT NULL,
  `delivery_date` date NOT NULL,
  `delivery_time` time NOT NULL,
  `delivery_method` varchar(50) NOT NULL,
  `payment_method` varchar(50) NOT NULL,
  `oder_status` int NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

ALTER TABLE `delivery`
  ADD PRIMARY KEY (`delivery_id`);


4. Kapila Bandara

-- Table structure for table `customer_feedback`

CREATE TABLE `customer_feedback` (
  `feedback_id` int NOT NULL,
  `member_id` int NOT NULL,
  `name` varchar(100) NOT NULL,
  `email` varchar(100) NOT NULL,
  `subject` varchar(200) NOT NULL,
  `message_type` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL,
  `message` varchar(500) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

ALTER TABLE `customer_feedback`
  ADD PRIMARY KEY (`feedback_id`),
  ADD KEY `feedback_member` (`member_id`);

-- Table structure for table `restaurant_rating`

CREATE TABLE `restaurant_rating` (
  `rating_id` int NOT NULL,
  `member_id` int NOT NULL,
  `name` varchar(100) NOT NULL,
  `rating_type` varchar(50) NOT NULL,
  `rating` int NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

ALTER TABLE `restaurant_rating`
  ADD PRIMARY KEY (`rating_id`),
  ADD KEY `rating_member` (`member_id`);
