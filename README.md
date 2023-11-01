def get_movie_by_index():
    # Display movies in the selected genre
    user_genre_choice = get_user_genre_choice()
    movies_in_genre = get_movies_in_genre(user_genre_choice)

    print(f"\nMovies in the genre {user_genre_choice}:")
    for index, movie in enumerate(movies_in_genre, start=1):
        print(f"{index}: {movie['title']}")

    # Ask user to select a movie by index
    selected_movie_index = int(input("\nPlease enter the index of the movie you want details for: ")) - 1  # Subtracting 1 to make it a valid Python index

    # Check if entered index is valid
    if 0 <= selected_movie_index < len(movies_in_genre):
        selected_movie = movies_in_genre[selected_movie_index]

        # Print details of the selected movie
        print("\nDetails of the selected movie:")
        for key, value in selected_movie.items():
            print(f"{key}, {value}")
    else:
        print("Invalid index provided!")

# Call the function to test it
get_movie_by_index()
