# PoSTagger Bahasa Indonesia

PoSTagging atau Part-of-Speech Tagging merupakan cara untuk memberi tag/penanda pada kata
berdasarkan kategori tertentu seperti kata kerja, kata benda atau kata keterangan. 
PoSTagger ini dibuat menggunakan metode Baseline dan HMM-Viterbi.

## Dataset
Dataset latih yang digunakan berasal dari korpus Part-Of-Speech Tag Bahasa Indonesia yang dapat
diunduh di http://bahasa.cs.ui.ac.id/postag/corpus . Dataset ini berisi 10.000 kalimat dalam Bahasa
Indonesia yang dibangun dari 256683 token dan telah dianotasi nilai POS-nya secara manual oleh
manusia.

## Metode Baseline
Model dengan metode Baseline menggunakan tag dengan emission probability frequency terbesar
dari setiap kata, tidak melihat kata sebelumnya ataupun kata sesudahnya. Model ini di uji dengan
dataset file “sample_postagged.txt” dan mendapatkan akurasi sebesar 93,4%.

## Metode HMM-Viterbi
Metode HMM-Viterbi merupakan metode berbasis pemodelan sekuens. HMM diterapkan untuk
menghitung transition probability dan emission probability . Sedangkan Viterbi digunakan untuk
menyelesaikan masalah decoding yaitu menentukan rangkaian yang paling mungkin dari
hidden-state untuk suatu kalimat. Viterbi bekerja secara dynamic programming untuk mengisi
probabilitas suatu state dengan rekursif.State yang paling mungkin dipilih dengan mengambil 
state yang memiliki probabilitas paling besar dari path state sebelumnya.
Model Viterbi diuji dengan dataset file “sample_postagged.txt” dan mendapatkan akurasi sebesar
97,3%. Viterbi memperhatikan kata sebelumnya, sehingga tag kata yang diprediksi lebih bagus.