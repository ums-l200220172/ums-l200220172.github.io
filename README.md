# ums-l200220172.github.io
from metaflow import FlowSpec, step

class CollegeFlow(FlowSpec):

    @step
    def start(self):
        """Memulai proses mengikuti kuliah di Informatika"""
        print("Langkah 1: Bayar SPP")
        self.next(self.register_courses)

    @step
    def register_courses(self):
        """Langkah kedua: Registrasi Mata Kuliah"""
        print("Langkah 2: Registrasi mata kuliah")
        self.next(self.attend_classes)

    @step
    def attend_classes(self):
        """Langkah ketiga: Mengikuti Perkuliahan"""
        print("Langkah 3: Mengikuti perkuliahan sesuai jadwal")
        self.next(self.midterms)

    @step
    def midterms(self):
        """Langkah keempat: Ujian Tengah Semester (UTS)"""
        print("Langkah 4: Mengikuti Ujian Tengah Semester (UTS)")
        self.next(self.finals)

    @step
    def finals(self):
        """Langkah kelima: Ujian Akhir Semester (UAS)"""
        print("Langkah 5: Mengikuti Ujian Akhir Semester (UAS)")
        self.next(self.get_khs)

    @step
    def get_khs(self):
        """Langkah terakhir: Mendapatkan Kartu Hasil Studi (KHS)"""
        print("Langkah 6: Mendapatkan Kartu Hasil Studi (KHS)")
        self.next(self.end)

    @step
    def end(self):
        """Selesai"""
        print("Proses selesai. Anda telah menyelesaikan semua langkah kuliah di Informatika!")

if __name__ == '__main__':
    CollegeFlow()
