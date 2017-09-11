## Chapter 2 Notes
# 2.2 
- Non-return to zero (NRZ): map the data value 1 onto the high signal and low data value 0 onto the low signal
-- long 0's and 1's ruins this by keeping the signal high or low for a long time.
-- known as baseline wander
-- clock recovery: depends on having lots of transitions in the signal, no matter what is being sent

- NRZI(Non- return to zero inverted): has the sender make a transition from the current signal to encode a 1 and stay at the current signal to encode a 0
-- this solves consecutive 1's but not zeros

- Manchester encoding: manages consecutives by doing exclusive OR of the NRZ- encoded data
-- doubles the rate at which signal transitions are made on the link
-- rate at which the signal changes: Baud rate
-- 50% efficient

- 4B/5B: insert extra bits into the bit stream so as to break up consecutives 1's and 0's. Eery 4 bits of data are encoded into a 5 bits
-- The 5-bit codes are selected so no one leading 0 and no more than 2 trailing zeros.
-- 80% efficient

## 2.3
# Bisync, PPP, DDCMP protocal: byte-oriented approach
- sends sentinel values
- (picture in book need to screenshot)
- error detection if frame is bad for FRAME ERROR

## 2.3.2 Bit oriented protocols (HDLC): bit protocol is not conscerned with boundaries
- bit stuffing
- 2.3.3 Clock based framing: Syncronous Optical Network. clock based framing

## 2.5 Reliable Transmission
# 2.5.2 Sliding window: sends a sequence number, SeqNum to each frame
- Send Window Size: SWS, gives the upper bound on the number of outstanding (unaknowledged) frames that the sender can transmit
- LAR: last achknowledgment received
- LFS denotes last frame sent
- (LFS - LAR <= SWS)
- Receiver maintains 3 variables
- Receive window size: RWS: upper bound on the number of out- of order frames that the receiver is willing to accept
- LAF denotes the sequence number of the Largest Acceptable Frame
- LFR denotes last frame received
- (LAF- LFR <=RWS)
