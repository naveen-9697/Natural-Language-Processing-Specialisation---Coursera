1. Condition Probabilities:</br>
Put simply, Conditional pro is the probability of something happening given something has already happened.<br>
    *e.g.: If you have a corpus of 20 tweets; in which 13 are of positive sentiment and 3 of them also have the word 'happy' and remaining 7 tweets are of negative sentiment. So, probability of tweet being positive sentiment given it has word 'happy' is:*
    <br></br><!--used line break here, since there was no space after text above and the equation below-->
    <!-- $\displaystyle  \text{P(positve | ‘happy’}) = \frac{\text{number of tweets in the corpus with word ‘happy’ in them}}{\text{number of positive tweets in the corpus with word ‘happy’}}$ -->
    <div align='center'><img src="https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%20%5Ctext%7BP(positve%20%7C%20%E2%80%98happy%E2%80%99%7D)%20%3D%20%5Cfrac%7B%5Ctext%7Bnumber%20of%20tweets%20in%20the%20corpus%20with%20word%20%E2%80%98happy%E2%80%99%20in%20them%7D%7D%7B%5Ctext%7Bnumber%20of%20positive%20tweets%20in%20the%20corpus%20with%20word%20%E2%80%98happy%E2%80%99%7D%7D"></div>
2. Naive Baye's Inference:</br>
Need to generate conditional probabilities(word occurences for a given class divided by total word counts for a given class) for all the unique words in the corpus for positive and negative classes; which will then be used to make inferences.</br>
e.g.: to classify the sentence 'I am happy today. I am learning NLP' into positive or negative sentiment,</br>

<!-- $\displaystyle \frac{\%\text{of postive tweets in corpus}}{\%\text{of postive tweets in corpus}} \left(\prod^{m}_{i=1} \frac{P(w_{i} | positive)}{P(w_{i} | negative)}\right) = \frac{0.50}{0.50} \times \left(\frac{0.24}{0.24} \times \frac{0.24}{0.24} \times \frac{0.24}{0.24} \times \frac{0.15}{0.08} \times \frac{0.24}{0.24} \times \frac{0.24}{0.24} \times \frac{0.08}{0.08}\right)$ --> <div align='center'><img src="https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle%20%20%5Cfrac%7B%5C%25%5Ctext%7Bof%20postive%20tweets%20in%20corpus%7D%7D%7B%5C%25%5Ctext%7Bof%20postive%20tweets%20in%20corpus%7D%7D%20%5Cleft(%5Cprod%5E%7Bm%7D_%7Bi%3D1%7D%20%5Cfrac%7BP(w_%7Bi%7D%20%7C%20positive)%7D%7BP(w_%7Bi%7D%20%7C%20negative)%7D%5Cright)%20%3D%20%5Cfrac%7B0.50%7D%7B0.50%7D%20%5Ctimes%20%5Cleft(%5Cfrac%7B0.24%7D%7B0.24%7D%20%5Ctimes%20%5Cfrac%7B0.24%7D%7B0.24%7D%20%5Ctimes%20%5Cfrac%7B0.24%7D%7B0.24%7D%20%5Ctimes%20%5Cfrac%7B0.15%7D%7B0.08%7D%20%5Ctimes%20%5Cfrac%7B0.24%7D%7B0.24%7D%20%5Ctimes%20%5Cfrac%7B0.24%7D%7B0.24%7D%20%5Ctimes%20%5Cfrac%7B0.08%7D%7B0.08%7D%5Cright)"></div>


***Note:*** word "today" is missing from above calculation, since words that doesn't exist in corpus of unique words will not be included in towards final calculation(*not included because the word it didn't occured only once*).</br>

3. Log-likelihood:</br>
Since the probabilites are always less than 1 and multiplying such numbers repeatedly might(its' actually very likely) result in very very small numbers; And this causes something called numerical underflow, which makes it hard for computers to store and deal with. So, to overcome this we should instead do addition than multiplication, using logs.
