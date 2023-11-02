## Report on the respective parts of the assignment

### Part 1

This part was quite straightforward. I followed the HuggingFace tutorial and managed to run the code smoothly, occasionally running into CUDA: out of memory error

### Part 2

This part's biggest challenge was to actually download the dataset as it is very big. I didn't upload the dataset to GitHub precisely because of its size. After a lot of struggles, I managed to download the dataset to my computer, but I didn't manage to upload all of its files to MLT GPU server. I had to add

`def clean_data(meta, datadir="train2017"):`<br>
&ensp;`return [x for x in meta if os.path.isfile("{}/{}".format(datadir, x['file_name']))]`

to the code, so that the machine doesn't try to access nonexistent files. The model worked quite well, guessing the example image right with 68% confidence

### Part 3

For this part, I chose to include dogs as the third class. With this additional class, the machine's performance dropped a bit, but it still managed to guess the class of an example image right with 35% confidence
