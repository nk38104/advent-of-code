Original source: [https://adventofcode.com/2022/day/6](https://adventofcode.com/2022/day/6)

## --- Day 6: Tuning Trouble ---

The preparations are finally complete; you and the Elves leave camp on foot and begin to make your way toward the <em style="color: yellow"><strong>star</strong></em> fruit grove.
As you move through the dense undergrowth, one of the Elves gives you a handheld <em><strong>device</strong></em>. He says that it has many fancy features, but the most important one to set up right now is the <em><strong>communication system</strong></em>.

However, because he's heard you have [significant](https://adventofcode.com/2016/day/6) [experience](https://adventofcode.com/2016/day/25) [dealing](https://adventofcode.com/2019/day/7) [with](https://adventofcode.com/2019/day/9) [signal-based](https://adventofcode.com/2019/day/16) [systems](https://adventofcode.com/2021/day/25), he convinced the other Elves that it would be okay to give you their one malfunctioning device - surely you'll have no problem fixing it.

As if inspired by comedic timing, the device emits a few <span title="The magic smoke, on the other hand, seems to be contained... FOR NOW!">colorful sparks</span>.

To be able to communicate with the Elves, the device needs to <em><strong>lock on to their signal</strong></em>. The signal is a series of seemingly-random characters that the ;device receives one at a time.

To fix the communication system, you need to add a subroutine to the device that detects a <em><strong>start-of-packet marker</strong></em> in the datastream. In the protocol being used by the Elves, the start of a packet is indicated by a sequence of <em><strong>four characters that are all different</strong></em>.

The device will send your subroutine a datastream buffer (your puzzle input); your subroutine needs to identify the first position where the four most recently received characters were all different. Specifically, it needs to report the number of characters from the beginning of the buffer to the end of the first such four-character marker.

For example, suppose you receive the following datastream buffer:

<pre>
<code>mjqjpqmgbljsphdztnvjfqwrcgsmlb</code>
</pre>

After the first three characters (<code>mjq</code>) have been received, there haven't been enough characters received yet to find the marker. The first time a marker could occur is after the fourth character is received, making the most recent four characters <code>mjqj</code>. Because <code>j</code> is repeated, this isn't a marker.

The first time a marker appears is after the <em><strong>seventh</strong></em> character arrives. Once it does, the last four characters received are <code>jpqm</code>, which are all different. In this case, your subroutine should report the value <code><em><strong>7</strong></em></code>, because the first start-of-packet marker is complete after 7 characters have been processed.

Here are a few more examples:

<ul>
    <li>
        <code>bvwbjplbgvbhsrlpgdmjqwftvncz</code>: first marker after character     <code><em><strong>5</strong></em></code>
    </li>
    <li>
        <code>nppdvjthqldpwncqszvftbrmjlhg</code>: first marker after character <code><em><strong>6</strong></em></code>
    </li>
    <li>
        <code>nznrnfrfntjfmvfwmzdfjlvtqnbhcprsg</code>: first marker after character <code><em><strong>10</strong></em></code>
    </li>
    <li>
        <code>zcfzfwzzqfrljwzlrfnpqdbhtmscgvjw</code>: first marker after character <code><em><strong>11</strong></em></code>
    </li>
</ul>

<em><strong>How many characters need to be processed before the first start-of-packet marker is detected?</strong></em>
</br>
</br>

## --- Part Two ---

Your device's communication system is correctly detecting packets, but still isn't working. It looks like it also needs to look for <em><strong>messages</strong></em>.

A <em><strong>start-of-message marker</strong></em> is just like a start-of-packet marker, except it consists of <em><strong>14 distinct characters</strong></em> rather than 4.

Here are the first positions of start-of-message markers for all of the above examples:

<ul>
    <li>
        <code>mjqjpqmgbljsphdztnvjfqwrcgsmlb</code>: first marker after character <code><em><strong>19</strong></em></code>
    </li>
    <li>
        <code>bvwbjplbgvbhsrlpgdmjqwftvncz</code>: first marker after character <code><em><strong>23</strong></em></code>
    </li>
    <li>
        <code>nppdvjthqldpwncqszvftbrmjlhg</code>: first marker after character <code><em><strong>23</strong></em></code>
    </li>
    <li>
        <code>nznrnfrfntjfmvfwmzdfjlvtqnbhcprsg</code>: first marker after character <code><em><strong>29</strong></em></code>
    </li>
    <li>
        <code>zcfzfwzzqfrljwzlrfnpqdbhtmscgvjw</code>: first marker after character <code><em><strong>26</strong></em></code>
    </li>
</ul>

<em><strong>How many characters need to be processed before the first start-of-message marker is detected?</strong></em>
