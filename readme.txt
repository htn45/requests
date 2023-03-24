from textblob import TextBlob

def get_nouns_tagcount (textstring):
    ''' Given a text string, we analyze it using textblob to find the number of tags and the noun phrases '''
    blob = TextBlob (textstring)
    # Count the tags
    tagcount = len (blob.tags)
    # Get the noun phrases
    p = blob.noun_phrases 
    return tagcount, p

speech1 = '''
Four score and seven years ago our fathers brought forth on this continent a new nation, conceived in Liberty, and dedicated to the proposition that all men are created equal.
Now we are engaged in a great civil war, testing whether that nation or any nation so conceived and so dedicated, can long endure. We are met on a great battle-field of that war. We have come to dedicate a portion of that field, as a final resting place for those who here gave their lives that that nation might live. It is altogether fitting and proper that we should do this.
But, in a larger sense, we can not dedicate—we can not consecrate—we can not hallow this ground. The brave men, living and dead, who struggled here, have consecrated it, far above our poor power to add or detract. The world will little note, nor long remember what we say here, but it can never forget what they did here. It is for us the living, rather, to be dedicated here to the unfinished work which they who fought here have thus far so nobly advanced. It is rather for us to be here dedicated to the great task remaining before us—that from these honored dead we take increased devotion to that cause for which they gave the last full measure of devotion—that we here highly resolve that these dead shall not have died in vain—that this nation, under God, shall have a new birth of freedom—and that government of the people, by the people, for the people, shall not perish from the earth.
'''
speech2 = '''
I’ve already decisively won many critical states, including massive victories in Florida, Iowa, Indiana, Ohio, to name just a few. We won these and many other victories despite historic election interference from big media, big money, and big tech. As everybody saw, we won by historic numbers, and the pollsters got it knowingly wrong. They got it knowingly wrong. We had polls that were so ridiculous and everybody knew it at the time.
There was no blue wave that they predicted. They thought there was going to be a big blue wave. That was false. That was done for suppression reasons. But instead there was a big red wave, and it’s been properly acknowledged actually by the media. They were, I think, very impressed, but that was after the fact. That doesn’t do us any good.
At the national level, our opponents major donors were Wall Street bankers and special interests. Our major donors were police officers, farmers, everyday citizens. Yet for the first time ever, we lost zero races in the House. I was talking to Kevin McCarthy today. He said he couldn’t believe it. Zero racist, very unusual thing, zero, and actually won many new seats with, I think, many more on the way.
'''

# We print out the noun phrases to see which ones are more inspiring and worthy of a leader
tags1, np1 = get_nouns_tagcount (speech1)   
print ("Abraham Lincoln's speech has {} tags and the noun phrases are:\n{}".format (tags1, np1))
tags2, np2 = get_nouns_tagcount (speech2)   
print ("Donald Trump's speech has {} tags and the noun phrases are:\n{}".format (tags2, np2))

# We check which speech has more tags (repeating words will end up with less tags?)
if (tags1 > tags2):
    print ("More tags in Lincoln's speech")
else:
    print ("More tags in Trump's speech")
if (len (np1) > len (np2)):
    print ("More moun phrases in Lincoln's speech")
else:
    print ("More noun phrases in Trump's speech")
