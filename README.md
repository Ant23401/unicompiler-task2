# unicompiler-task2
pip install tkinter
from pytube import YouTube
url = 'https://www.youtube.com/watch?v=DODLEX4zzLQ'
yt_video = YouTube(url)
print(yt_video.title)
from pytube import YouTube
url = 'https://www.youtube.com/watch?v=DODLEX4zzLQ'
yt_video = YouTube(url)
print(yt_video.thumbnail_url)
from pytube import YouTube

url = 'https://www.youtube.com/watch?v=DODLEX4zzLQ'
yt_video = YouTube(url)
# this method will download the highest resolution that video is available
yt_video = my_video.streams.get_highest_resolution()
methodyt_video.download()

print('your video is downloaded successfully')
from pytube import YouTube
url = 'https://www.youtube.com/watch?v=DODLEX4zzLQ'
yt_video = YouTube(url)

# here we are fetching a list of all the video resolution
videos = yt_video.streams.all()
# we are using enumerate to get the index number
res_list = list(enumerate(videos))
for i in res_list:
    print(i)

resolution = int(input("Enter the index number of the video : "))
videos[resolution].download()
print('your video is downloaded successfully')
# for getting only audio list
videos = yt_video.streams.filter(only_audio=True)
# for getting only video list
videos = yt_video.streams.filter(only_audio=True)
from pytube import Playlist

playlist = Playlist('https://www.youtube.com/playlist?list=PLG9-DrM4Coeq7vdqBb84sNRZZHEUfQDcK')

print('Number of videos in playlist: %s' % len(playlist.video_urls))
playlist.download_all()
# import required libraries
import string
import tkinter as tk
from tkinter import *
from tkinter import messagebox
from tkinter import filedialog
from cv2 import dft
from pytube import YouTube

def createwidgits():
    # creating a button
    link_label = Label(root, text ='Paste URL: ', bg="#999999")
    # placing the label
    link_label.grid(row=1, column=0, pady=10, padx=10)

    # creating a entry point
    root.link_text = Entry(root, width=60 , textvariable=video_link)
    # placing the point
    root.link_text.grid(row=1, column=1,pady=10, padx=10)
  # creating a entry point
    root.link_text = Entry(root, width=60 , textvariable=video_link)
    # placing the point
    root.link_text.grid(row=1, column=1,pady=10, padx=10)

    # creating a destination label
    destination_label = Label(root, text ='Destination: ', bg="#999999")
    # placing the label
    destination_label.grid(row=2, column=0, pady=10, padx=10)

    # creating a destination box
    root.destination_label = Entry(root, width=60 , textvariable=Download_path)
    # placing the box
    root.destination_label.grid(row=2, column=1,pady=10, padx=10)

    # create a browse button
    browse_but = Button(root, text="Browse", command=browse, width=10, bg="#ffffff")
    # place the button
    browse_but.grid(row=2, column=2, pady=10, padx=10)

    # create a download button
    download_but = Button(root, text="Download", command=download_video, width=15, bg="#ff0000")
    # place the button
    download_but.grid(row=3, column=1, pady=3, padx=3)
    # create youtube video download function
def download_video():

    url = video_link.get()
    folder = Download_path.get()
    get_video = YouTube(url)
    get_stream = get_video.streams.first()
    get_stream.download(folder)

    messagebox.showinfo("Your video downloaded successfully")

# creating an instance
root = tk.Tk()

# size of the window
root.geometry("600x120")
root.resizable(False,False)
# name of the window
root.title("downloader")
# colors of the window
root.config(background="#999999")

video_link = StringVar()
Download_path = StringVar()

createwidgits()

root.mainloop()
