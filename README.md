
After learning about left-neighbour encoding, I chose to try that. In it, we look at the pixel to the left, use that value to choose one of the 256 probability models, and encode the current pixel's difference value. Becaues the nearby pixels are usually similar, we use pixels with similar behaviors to improve our efficiency.

We'll still encode one pixel at the time, just not using a single probability model anymore. Pixels near each other usually look similar, so grouping by left-neighbor brightness gives more accurate probabilities, and arithmetic coding can store data in fewer bits.

Using cargo run -p assgn1 -- -check_decode for bourne.mp4, we get 10 frames decoded, Average size: 5,893,402 bits per frame, Compression ratio: 2.81

Using another popular video (safe.mp4, check it out!), we get 10 frames encoded, average size (bits): 6516277, compression ratio: 2.55