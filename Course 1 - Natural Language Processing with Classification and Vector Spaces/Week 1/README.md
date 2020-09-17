<b>Summary of this week:</b>
<ol>
    <li>Preprocessing text, tweets mainly</li>
        <ul>
            <li>Normalisg case of words,</li>
            <li>Removing punctuation, '@', '$', '#'(from hashtags), 'RT' tags, URLs and names using regular expressions,</li>
            <li>Removing Stop words,</li>
            <li>Reducing words to their base form, known as Stemming.</li>
            <li>Then tokenise sentences</li>
        </ul>
    <li>Then, Creating corpus from unique words in all the sentences(tweets), called toknising</li>
        <ul>
            <li>with Count Vectorisation and</li>
            <li>with frequency counts.</li>
        </ul>
    <li>Then matrix will be created as follows:
        <ul>
            <li>With count vectorisation:</li>
                <p>For each tweet, which is each row, rows will be filled with counts, that is number of times each word in a respective column apperas in current tweet.</p>
            <li>With frequency counts:</li>
                <p>
                    This will be a bit different. Initially a frequency dictionary has to be built.
                        <blockquote>
                            frequency dictionary building goes like this: it will contain word, class it belongs to and word's frequency. for example, {('happy',1):23, ('happy',0):3}. That dictionary tells, a word 'happy' in positive tweets has occured 23 times and 3 times in negative tweets.
                        </blockquote>
                    Then final matrix will just be a 3 dimensional feature matrix with targets in another matrix. This 3D matrix will have bias in first column(1 for positive tweets and 0 for negative tweets), second column with sum of frequencies for positive words for current tweet while third column will have sum of frequencies of negative words.
                </p>
        </ul>
    </li>
</ol>
