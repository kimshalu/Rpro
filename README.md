# Rpro
#A code on movie booking being written in R language 

# Define enums as vectors or factors in R
SeatStatus <- c("SEAT_BOOKED", "SEAT_NOT_BOOKED")
MovieStatus <- c("MOVIE_AVAILABLE", "MOVIE_NOT_AVAILABLE")
MovieType <- c("ENGLISH", "HINDI")
SeatType <- c("NORMAL", "EXECUTIVE", "PREMIUM", "VIP")
PaymentStatus <- c("PAID", "UNPAID")

# Define classes as lists in R
User <- list(
  userId = integer(),
  name = character(),
  dateOfBirth = as.Date(character()), # Note: as.Date() doesn't make sense here
  mobNo = character(),
  emailId = character(),
  sex = character()
)

Movie <- list(
  movieId = integer(),
  theaterId = integer(),
  movieType = factor(MovieType),
  movieStatus = factor(MovieStatus)
)

Theater <- list(
  theaterId = integer(),
  theaterName = character(),
  address = list(), # Assuming you might want to define address as a separate class
  movies = list(),
  rating = numeric()
)

Booking <- list(
  bookingId = integer(),
  userId = integer(),
  movieId = integer(),
  bookedSeats = list(),
  amount = integer(),
  status_of_payment = factor(PaymentStatus),
  booked_date = as.Date(character()), # Note: as.Date() doesn't make sense here
  movie_timing = character() # Assuming Time is a character string representing time
)

Address <- list(
  city = character(),
  pinCode = character(),
  state = character(),
  streetNo = character(),
  landmark = character()
)

SeatBook <- list(
  transaction_obj = list(),
  seats = logical(total_seats), # Assuming total_seats is defined elsewhere
  place = character(),
  ticketType = character(),
  
  check_availability = function() {
    # Function body to be defined
  },
  
  position_of_seat = function() {
    return(seat_pos_in_theater) # Assuming seat_pos_in_theater is defined elsewhere
  },
  
  multiple_tickets = function() {
    # Function body to be defined
  },
  
  final_booking = function() {
    place <- position_of_seat()
    if (single_ticket) {
      # Continue with single ticket booking
      # Code to be defined
    } else {
      multiple_tickets()
    }
    transaction_obj$pay(ticketType, seats_booked, place) # Assuming pay is a method of transaction_obj
  }
)
