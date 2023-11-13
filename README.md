# Roshan Hoffmann 
# 11/12/2023

# Create a new GitHub repository for UFO data
# 1. Create a GitHub repository for the UFO data named – dataset_ufo

# Load necessary libraries
library(usethis)

# Set up GitHub repo details
repo_name <- "dataset_ufo"
repo_description <- "UFO Sightings Dataset"
github_user <- "rnhoffmann"

# Create GitHub repo
create_repo(repo_name, description = repo_description, private = FALSE)

# Set working directory to the project folder
setwd("~/path/to/your/project")

# Initialize a new R project
usethis::use_course("dataset_ufo")

# Set up project structure
dir.create("code")
dir.create("archive")

# Copy README.md to code and archive folders
file.copy("README.md", c("code/README.md", "archive/README.md"), overwrite = TRUE)

# Commit changes
usethis::use_git()
usethis::use_git_ignore(c("R/"))

# Commit initial changes
usethis::use_git_commit("Initial commit")

# Push to GitHub
usethis::use_github(username = rnhoffmann, repo = repo_name)

