# googleflights
Google flights scraper

This script allows you to find the cheapest individiual roundtrip ticket from one airport to another - this includes price and itinerary. It also allows you to 1. specify your departing destination and 2. pull price/itinerary flight information based on a list of the faa's top US airports (https://www.faa.gov/airports/planning_capacity/passenger_allcargo_stats/passenger/). This webpage contains an xlsx file that, when 'Answer' variable = Yes, downloads to your local device. Once downloaded, the script looks at the index value variables, 'start_point' and 'end_point', and pulls those from the list of IATA airport codes contained in the xlsx file.

Provided below are the variables contained in the script + notes:

# WHERE DO YOU WANT TO GO ---- Departure/Arrival Flight Destination Parameters (Required)
dep_city = ('San Francisco')
arv_city = ('Denver') 

# DO YOU WANT TO CHOOSE ARRIVAL DESTINATION BASED BY THE TOP UNITED STATES AIRPORTS?
Answer = ('yes') # INPUT yes/no --> 'no' will return the cheapest roundtrip flight of the dep/arv cities from above

# IF ABOVE ANSWER IS YES, CHOOSE YOUR STARTING/ENDING POINTS. FOR EXAMPLE, CHOOSE 0 IF YOU'D LIKE TO START WITH THE MOST
# POPULAR AIRPORT CONTAINED IN THE XLSX FILE, THEN SPECIFY ENDPOINT TO DETERMINE # OF AIRPORTS TO SEARCH
# EXAMPLE : {IF start_point = 0 and end_point = 20, then you'll look through the top 21 airports}
start_point = 0
end_point   = 50 
# only limitation here is that the max range of airports that can be scraped at once is: 55 airports
# in short, the script will throw an error if the start point exceeds a search of >55 airports

# WHEN DO YOU WANT TO LEAVE -- Departure/Arrival Flight Date Parameters (Required)
dep_date = '7/11/2019'
arv_date = '7/14/2019'

# HOW MANY STOPS DO YOU WANT? - Put 0 for Non-Stop flight { 2 is the MAX }
num_stops = '2'

# FOR YOUR DEPARTING FLIGHT --- WHAT TIME DO YOU WANT TO LEAVE AT? ~ ** Must be at least a 3 hour window! ** ~ (Required)
dep_leave_time_1 = '6:15AM'
dep_leave_time_2  = '8:45pM'

# DO YOU WANT TO DOWNLOAD YOUR DATA?
csv_file_download = 'Yes'

# IS THERE A DIFFERENT AIRPORT DISPLAYING IN RESULTS? CHANGE AIRPORT BY ADJUSTING LIST INDEX (0 is default) 
# THAT YOU SEEN IN COMMAND LINE. NOTE: ONLY APPLICABLE IF CHOOSING CUSTOM DEPARTURE/ARRIVAL DESTINATIONS
dep_IATA_index = '0'
arv_IATA_index = '2'
