# man's template_instapy

""" Quickstart script for InstaPy usage """
# imports
from instapy import InstaPy
from instapy.util import smart_run
from random import sample
from random import randint
from time import sleep


def get_likes_n_times():
    return randint(27, 35)

def get_follow_n_times():
    return randint(41, 59)

def get_unfollow_n_times():
    return randint(34, 49)

def get_random_sleep():
    return randint(60, 440)

# already liked: familiaanimal
tags = []

accounts_to_follow = []

my_friends = []

# locations = [
# '214275746', '214642445', '228513534', '222986128', '237482739', '228563576']
# seleciona 3 tags da lista de tags p/ trabalhar
def get_accounts_to_follow():
    return sample(set(accounts_to_follow), 3)

def get_tags():
    return sample(set(tags), 3)

# login credentials
insta_username = 'x'
insta_password = 'x'

# set headless_browser=True to run InstaPy in the background
session = InstaPy(username=insta_username,
                  password=insta_password,
                  proxy_address='0.0.0.0',
                  proxy_port=x,
                  use_firefox=True,
                  headless_browser=False,
                  nogui=True)
with smart_run(session):
    # general settings
    session.set_ignore_users(my_friends)
    session.set_dont_include(my_friends)
    session.set_relationship_bounds(enabled=True,
                                    delimit_by_numbers=True,
                                    max_followers=5000,
                                    min_followers=40,
                                    min_following=30)

    # activity
    session.follow_user_followers(get_accounts_to_follow(), amount=get_follow_n_times(), randomize=False, sleep_delay=60)
    sleep(get_random_sleep())
    # session.like_by_tags(get_tags(), amount=get_likes_n_times())
    session.follow_user_followers(get_accounts_to_follow(), amount=get_follow_n_times(), randomize=False, sleep_delay=60)
    sleep(get_random_sleep())
    session.follow_user_followers(get_accounts_to_follow(), amount=get_follow_n_times(), randomize=False, sleep_delay=60)
    sleep(get_random_sleep())
    session.follow_user_followers(get_accounts_to_follow(), amount=get_follow_n_times(), randomize=False, sleep_delay=60)
