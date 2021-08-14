# Welcome!

InterCom (`intercom`) is a low-latency full-duplex intercom(municator) designed for the transmission of media (audio) between networked users. It is implemented in Python and designed as a set of layers that provide an incremental functionality, following a multilevel (one-to-one) inheritance model:

1. `minimal`: records/plays raw (CD quality) audio and send/receive it to/from another `intercom` instance.
2. `buffer`: delays the playing of chunks of audio to hide the network jitter.
3. `compress`: uses [DEFLATE](https://en.wikipedia.org/wiki/Deflate) to compress the chunks of audio.
4. `br_control`: uses [quantization](https://en.wikipedia.org/wiki/Quantization_(signal_processing)) to control the transmission [bit-rate](https://en.wikipedia.org/wiki/Bit_rate).
5. `stereo_coding`: removes spatial (inter-channel) [redundancy](https://en.wikipedia.org/wiki/Redundancy_(information_theory)).
6. `temporal_coding`: removes temporal (intra-channel) redundancy.
7. `threshold`: removes phycho-acoustic redundancy generated by the expected [threshold of hearing](https://en.wikipedia.org/wiki/Psychoacoustics#Limits_of_perception).
8. `t_masking`: removes phycho-acoustic redundancy generated by the expected [temporal masking effect](https://en.wikipedia.org/wiki/Auditory_masking#Temporal_masking).
9. `s_masking`: removes phycho-acoustic redundancy generated by the expected [simultaneous masking effect](https://en.wikipedia.org/wiki/Auditory_masking#Simultaneous_masking).
