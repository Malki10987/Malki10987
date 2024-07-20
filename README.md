# Load the extracted audio
extracted_audio_path = "/mnt/data/extracted_audio.wav"
audio_clip = mp.AudioFileClip(extracted_audio_path)

# The poem text to be added
poem_text = """
يا حلمي الطائر في السما الغالية
أريد أن أكون لاعبًا، أحيا الأماني السامية

لكن الأهل في دربٍ آخر ساروا
يريدون لي العلم في أمريكا اختاروا

أقول لهم يا أهلي هذا قلبي وما يهوى
هنا في بلدي أريد أن أكون، بين الأهل والأحباب أروى

سأظل أركض خلف الكرة، في كل ميدان
حتى لو كان الأمر عسيرًا، سأصمد مهما كان

فالعلم نورٌ لكن حلمي له جذور
في ملاعب وطني أود أن أزهر، مثل الزهور
"""

# Initialize TTS engine and save poem as audio
tts_audio_path = "/mnt/data/poem_tts.wav"
engine.save_to_file(poem_text, tts_audio_path)
engine.runAndWait()

# Load the TTS poem audio
poem_audio_clip = mp.AudioFileClip(tts_audio_path)

# Combine the extracted audio with the TTS poem audio
combined_audio = mp.concatenate_audioclips([audio_clip, poem_audio_clip])

# Save the combined audio to a file
combined_audio_path = "/mnt/data/combined_audio.mp3"
combined_audio.write_audiofile(combined_audio_path)

combined_audio_path
