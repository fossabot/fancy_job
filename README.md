# Daily Number Incrementer

A Python script that automatically increments a number in a text file, commits the change to Git, and updates a cron job to run the script at a new random time daily. Perfect for maintaining a daily commit streak or tracking sequential values with a dynamic schedule.

## Setup

1. Clone this repository:

   ```bash
   git clone https://github.com/Shogun89/fancy_job
   cd fancy_job
   ```

2. Run the script

   The script can be run without any dependencies besides the Python standard library:

   ```bash
   python update_number.py
   ```

   You might want to run the script manually for the first time to verify it works before setting up a cron job.

3. **(Optional)** Use LLM-based commit messages

   If you prefer AI-generated commit messages, you'll need to install [uv](https://docs.astral.sh/uv) to manage dependencies. The first time you run it, it will download the required packages and a large language model from Hugging Face.

   ```bash
   FANCY_JOB_USE_LLM=true uv run python update_number.py
   ```

4. Set up a cron job to run the script daily:

   ```bash
   crontab -e
   ```

   Add the following line to the crontab file:

   ```bash
   0 6 * * * cd /path/to/your/repo && python update_number.py
   # or with LLM
   0 6 * * * cd /path/to/your/repo && FANCY_JOB_USE_LLM=true uv run python update_number.py
   ```

   This will initially run the script at 6am the next day.

## Usage

The script will increment the number in [`number.txt`](number.txt) and commit the change to Git. You can modify the script to increment by any value or use a different file to store the number.

By running this, you'll be able to get a fancy streak on your GitHub profile and get a job!

![How to get a job](get_a_job.jpg)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fericsherrill-made4net%2Ffancy_job.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fericsherrill-made4net%2Ffancy_job?ref=badge_shield)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fericsherrill-made4net%2Ffancy_job.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fericsherrill-made4net%2Ffancy_job?ref=badge_large)