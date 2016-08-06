# Jazzomat - Audio Analysis - Raw Data

## Summary

On this page, we provide raw analysis data from the score-informed audio analysis
methods applied on the recordings of the Weimar Jazz Database.

## Database version

The current results were extracted from 299 solos included in
version 1.2 of the Weimar Jazz Database (Aug 2016).

## Data

* [Solo-wise f0 contours + corresponding time-stamps stored as CSV files](wjazzd_v_1_2/raw_f0)
* [Solo-wise intensity contours + corresponding time-stamps stored as CSV files](wjazzd_v_1_2/raw_intensity)
* [Solo transcriptions (pitch, onset (s), duration(s))](wjazzd_v_1_2/score_csv)
* Analysis results as pandas DataFrame
  * *df_solos*: Solo-wise metadata
    * Parameters from human transcription
      * 'title': solo title
      * 'performer': soloist name
      * 'avgtempo': average tempo (bpm)
      * 'instrument': instrument short label
      * 'filename_*': audio file names
      * 'base_name': solo base name (same column exists in *df_notes*)
      * 'recording_year': recording year
    * Parameters from automatic analysis
      * 'tuning_frequency': estimated tuning frequency (Hz) using the NNLS Chroma VAMP plugin on the
     solo backing track (with the solo instrument being removed using source separation methods)
  * *df_notes* Note-wise metadata  
    * Parameters from human transcription
      * 'onset': note onset (sec)
      * 'duration': note duration (sec)
      * 'pitch': MIDI pitch
      * 'metrical_position': metrical position (see (Jazzomat website)[http://jazzomat.hfm-weimar.de/] for more information)
      * 'phraseid': phrase ID
      * 'base_name': solo base name (see *df_solos*)
                                        'base_name': base_name})  
      * 'solo_id': Solo ID
      * 'note_id': Note ID (note: this does not correspond to the note ID in the wjazzd.db since here, only notes longer than 50 ms were processed, correspondance to notes in the wjazzd.db should best be created via onset & pitch)
    * Parameters from automatic analysis
      * 'intensity_max': Maximum over frame-wise intensity values over note duration
      * 'intensity_median': Median over frame-wise intensity values over note duration
      * 'intensity_std': Standard deviation over frame-wise intensity values over note duration
      * 'intensity_temp_centroid': Temporal centroid over frame-wise intensity values over note duration
      * 'intensity_rel_peak_pos': Relative peak position [0, 1] over frame-wise intensity values over note duration
      * 'intensity_5_to_95_percentile_range': Note-wise peak intensity (scaled to [0, 1] based on 5% / 95% percentiles)
      * 'f0_mod_range_cent': f0 modulation range (cent)
      * 'f0_av_f0_dev_median': median over frame-wise f0-deviation from annotated pitch (cent)                                         * 'f0_av_f0_dev_mean': mean over frame-wise f0-deviation from annotated pitch (cent)
      * 'f0_av_abs_f0_dev_median': median over absolute frame-wise f0-deviation from annotated pitch (cent)  
      * 'f0_av_abs_f0_dev_mean': median over absolute frame-wise f0-deviation from annotated pitch (cent)
      * 'f0_iqr_cent_rel': inter-quartile range over frame-wise f0-deviation from annotated pitch (cent)
      * 'f0_lin_f0_slope': approximation of linear slope over frame-wise f0-deviation (using numpy.polyfit())
      * 'f0_median_freq_gradient_overal': mean frequency gradient over frame-wise f0 values (Hz)
      * 'f0_median_freq_gradient_first_half': mean frequency gradient over frame-wise f0 values (Hz) in first half of note duration
      * 'f0_median_freq_gradient_second_half': mean frequency gradient over frame-wise f0 values (Hz) in second half of note duration
      * 'f0_ratio_of_descending_segments': ratio of segments of current f0 contours with positive gradients
      * 'f0_ratio_of_ascending_segments': ratio of segments of current f0 contours with negative gradients
      * 'f0_ratio_of_constant_segments': ratio of segments of current f0 contours with constant frequency
      * 'f0_av_rel_segment_len': average segment length (frames)/ note duration (frames)       
      * 'f0_mod_freq_hz': f0 modulation frequency (Hz) based on autocorrelation search
      * 'f0_mod_dom': dominance of f0 modulation   
      * 'f0_mod_num_periods': number of modulation half periods

  * [Exported as CSV](wjazzd_v_1_2/pandas_dataframes_csv)
  * [Exported via pickle](wjazzd_v_1_2/pandas_dataframes_pickle) (open with *pandas.read_pickle()*)
*
 * pandas_dataframes_csv_v_1_2
  *
* "Jazz solo analysis between music information retrieval, music psychology, and jazz research." - ISMIR Conference, August, 7, 2016
 * Part 1
 * Part 2
 * [Part 3 - Score-informed Solo Analysis (slides)](ISMIR_2016_Tutorial/ISMIR_2016_Jazzomat_Tutorial_Part_3.pdf)

## Research Projects

* [j-i-r (Jazz Information Retrieval) project](http://music.columbia.edu/cmc/j-i-r/)
* [j-DISC](http://jdisc.columbia.edu/)
* [Jazzomat Research Project](http://jazzomat.hfm-weimar.de/)
* [Flow Machines](http://www.flow-machines.com/)
* [Continuator](http://francoispachet.fr/continuator/continuator.html)
* [rhythm changes](http://www.rhythmchanges.net/)

## References

* See the BibTeX file [references.bib](references.bib) for an extensive overview of related rerferences (articles, papers, books, etc.)
* [Zotero - jazz research group](https://www.zotero.org/groups/jazz-research)
* [Bob Keller's Jazz Page](https://www.cs.hmc.edu/~keller/jazz/)

## Software / Tools

### Symbolic Music Analysis

* [Music21](http://web.mit.edu/music21/)
* [jMIR](http://jmir.sourceforge.net/)
* [MIDI Toolbox](https://www.jyu.fi/hum/laitokset/musiikki/en/research/coe/materials/miditoolbox)
* [The Humdrum Toolkit](http://www.musiccog.ohio-state.edu/Humdrum/)
* [Themefinder](http://www.themefinder.org/)
* [musipedia](http://www.musipedia.org/js_piano.html)
* [Music Ngram Viewer](http://www.peachnote.com/#!nt=singleNoteAffine&npq=62+0+1+2+0+-2+-1+-2+-2)
* [Kooplet](http://www.kooplet.com/cgi-bin/kooplet/search.pl)

## Transcriptions ##

* [Saxopedia](http://www.saxopedia.com/)
* [Jazz Trumpet Transcriptions](http://pubcs.free.fr/jg/jazz_trumpet_transcriptions_jacques_gilbert_english.html)
* [Scooby-Sax](http://www.scooby-sax.com/Transcriptions.html)
* [Michael Brecker Live Recordings](http://www.michaelbreckerliverecordings.com/)
* [Jazz Trumpet Solos](http://www.jazztrumpetsolos.com/)
* [Free Jazz Institute (Themes)](http://freejazzinstitute.com/showposts.php?dept=transcriptions)

## Conferences & Workshops & Summerschools ##

## Blogs ##

* [Harderbop Blog](https://harderbop.blogspot.de/)
* [Savage Music](https://savagemusic.wordpress.com/)

## Misc ##

* [Jazzadvice](http://www.jazzadvice.com/)
* [Interview with Lee Konitz](https://ethaniverson.com/rhythm-and-blues/18-with-lee-k/)
