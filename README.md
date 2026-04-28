from kivymd.app import MDApp
from kivy.lang import Builder
from kivy.uix.screenmanager import ScreenManager, Screen
from kivy.core.window import Window

Window.size = (360, 640)

KV = '''
ScreenManager:
    MenuScreen:
    KalkulatorScreen:
    TentangScreen:

<MenuScreen>:
    name: "menu"

    MDBoxLayout:
        orientation: "vertical"
        md_bg_color: 0.1, 0.1, 0.2, 1

        Widget:
            size_hint_y: 0.1

        MDBoxLayout:
            orientation: "vertical"
            size_hint_y: 0.45
            padding: 20

            MDIcon:
                icon: "Numenius"
                halign: "center"
                theme_text_color: "Custom"
                text_color: 1, 0.6, 0, 1
                font_size: "80sp"

            MDLabel:
                text: "Numenius"
                halign: "center"
                font_style: "H4"
                theme_text_color: "Custom"
                text_color: 1, 1, 1, 1
                bold: True

            MDLabel:
                text: "Hitung Jenius  "
                halign: "center"
                font_style: "Subtitle1"
                theme_text_color: "Custom"
                text_color: 0.7, 0.7, 0.9, 1

        Widget:
            size_hint_y: 0.05

        MDBoxLayout:
            orientation: "vertical"
            size_hint_y: 0.3
            padding: [40, 0]
            spacing: 15

            MDRaisedButton:
                text: "MULAI HITUNG"
                font_size: "18sp"
                size_hint_x: 1
                size_hint_y: None
                height: "55dp"
                md_bg_color: 1, 0.5, 0, 1
                on_release: root.manager.current = "kalkulator"

            MDRaisedButton:
                text: "TENTANG APLIKASI"
                font_size: "16sp"
                size_hint_x: 1
                size_hint_y: None
                height: "55dp"
                md_bg_color: 0.2, 0.4, 0.8, 1
                on_release: root.manager.current = "tentang"

        Widget:
            size_hint_y: 0.1

        MDLabel:
            text: "© 2025 CalcSimple | ITKA"
            halign: "center"
            font_style: "Caption"
            theme_text_color: "Custom"
            text_color: 0.5, 0.5, 0.7, 1
            size_hint_y: 0.05


<KalkulatorScreen>:
    name: "kalkulator"

    MDBoxLayout:
        orientation: "vertical"
        md_bg_color: 0.08, 0.08, 0.08, 1
        spacing: 0

        # ---- HEADER ----
        MDBoxLayout:
            orientation: "horizontal"
            size_hint_y: None
            height: "50dp"
            md_bg_color: 0.1, 0.1, 0.2, 1
            padding: [10, 5]

            MDIconButton:
                icon: "arrow-left"
                theme_text_color: "Custom"
                text_color: 1, 1, 1, 1
                on_release: root.manager.current = "menu"

            MDLabel:
                text: "Kalkulator"
                halign: "left"
                font_style: "H6"
                theme_text_color: "Custom"
                text_color: 1, 1, 1, 1
                bold: True

        MDBoxLayout:
            orientation: "vertical"
            size_hint_y: None
            height: "140dp"
            md_bg_color: 0.05, 0.05, 0.05, 1
            padding: [20, 10]

            MDLabel:
                id: layar_ekspresi
                text: "0"
                halign: "right"
                font_style: "H6"
                theme_text_color: "Custom"
                text_color: 0.7, 0.7, 0.7, 1

            MDLabel:
                id: layar_hasil
                text: "0"
                halign: "right"
                font_style: "H3"
                theme_text_color: "Custom"
                text_color: 1, 1, 1, 1
                bold: True

        
        MDGridLayout:
            cols: 4
            rows: 5
            size_hint_y: 1
            padding: 6
            spacing: 6

            # === BARIS 1 ===
            MDRaisedButton:
                text: "C"
                font_size: "20sp"
                size_hint: 1, 1
                md_bg_color: 0.8, 0.1, 0.1, 1
                on_release: root.tekan_tombol("C")

            MDRaisedButton:
                text: "DEL"
                font_size: "16sp"
                size_hint: 1, 1
                md_bg_color: 0.4, 0.1, 0.1, 1
                on_release: root.tekan_tombol("DEL")

            MDRaisedButton:
                text: "%"
                font_size: "20sp"
                size_hint: 1, 1
                md_bg_color: 0.3, 0.3, 0.3, 1
                on_release: root.tekan_tombol("%")

            MDRaisedButton:
                text: "/"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 1, 0.5, 0, 1
                on_release: root.tekan_tombol("/")

            # === BARIS 2 ===
            MDRaisedButton:
                text: "7"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("7")

            MDRaisedButton:
                text: "8"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("8")

            MDRaisedButton:
                text: "9"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("9")

            MDRaisedButton:
                text: "X"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 1, 0.5, 0, 1
                on_release: root.tekan_tombol("*")

            # === BARIS 3 ===
            MDRaisedButton:
                text: "4"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("4")

            MDRaisedButton:
                text: "5"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("5")

            MDRaisedButton:
                text: "6"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("6")

            MDRaisedButton:
                text: "-"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 1, 0.5, 0, 1
                on_release: root.tekan_tombol("-")

            # === BARIS 4 ===
            MDRaisedButton:
                text: "1"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("1")

            MDRaisedButton:
                text: "2"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("2")

            MDRaisedButton:
                text: "3"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("3")

            MDRaisedButton:
                text: "+"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 1, 0.5, 0, 1
                on_release: root.tekan_tombol("+")

            MDRaisedButton:
                text: "0"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("0")

            MDRaisedButton:
                text: "00"
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol("00")

            MDRaisedButton:
                text: "."
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.2, 0.2, 0.2, 1
                on_release: root.tekan_tombol(".")

            MDRaisedButton:
                text: "="
                font_size: "22sp"
                size_hint: 1, 1
                md_bg_color: 0.1, 0.7, 0.1, 1
                on_release: root.tekan_tombol("=")


<TentangScreen>:
    name: "tentang"

    MDBoxLayout:
        orientation: "vertical"
        md_bg_color: 0.1, 0.1, 0.2, 1

        MDBoxLayout:
            orientation: "horizontal"
            size_hint_y: None
            height: "50dp"
            md_bg_color: 0.15, 0.15, 0.3, 1
            padding: [10, 5]

            MDIconButton:
                icon: "arrow-left"
                theme_text_color: "Custom"
                text_color: 1, 1, 1, 1
                on_release: root.manager.current = "menu"

            MDLabel:
                text: "Tentang Aplikasi"
                font_style: "H6"
                theme_text_color: "Custom"
                text_color: 1, 1, 1, 1
                bold: True

        MDScrollView:
            MDBoxLayout:
                orientation: "vertical"
                adaptive_height: True
                padding: 30
                spacing: 15

                MDIcon:
                    icon: "calculator"
                    halign: "center"
                    theme_text_color: "Custom"
                    text_color: 1, 0.6, 0, 1
                    font_size: "60sp"
                    size_hint_y: None
                    height: "80dp"

                MDLabel:
                    text: "CalcSimple v1.0"
                    halign: "center"
                    font_style: "H5"
                    theme_text_color: "Custom"
                    text_color: 1, 1, 1, 1
                    bold: True
                    size_hint_y: None
                    height: "40dp"

                MDLabel:
                    text: "Kalkulator Sederhana"
                    halign: "center"
                    theme_text_color: "Custom"
                    text_color: 0.7, 0.7, 1, 1
                    size_hint_y: None
                    height: "30dp"

                MDSeparator:
                    size_hint_y: None
                    height: "2dp"

                MDLabel:
                    text: "Informasi Aplikasi"
                    font_style: "H6"
                    theme_text_color: "Custom"
                    text_color: 1, 0.6, 0, 1
                    size_hint_y: None
                    height: "35dp"

                MDLabel:
                    text: "Aplikasi    : CalcSimple\\nVersi         : 1.0\\nBahasa      : Python\\nFramework : KivyMD\\nPlatform    : Android"
                    theme_text_color: "Custom"
                    text_color: 0.9, 0.9, 0.9, 1
                    size_hint_y: None
                    height: "120dp"

                MDSeparator:
                    size_hint_y: None
                    height: "2dp"

                MDLabel:
                    text: "Informasi Akademik"
                    font_style: "H6"
                    theme_text_color: "Custom"
                    text_color: 1, 0.6, 0, 1
                    size_hint_y: None
                    height: "35dp"

                MDLabel:
                    text: "Mata Kuliah  : Pengembangan Aplikasi Mobile\\nSemester      : IV\\nJurusan         : Teknologi Informasi\\nKampus         : ITKA\\nDosen            : M. Khairul Hadi, S.Kom., M.Pd."
                    theme_text_color: "Custom"
                    text_color: 0.9, 0.9, 0.9, 1
                    size_hint_y: None
                    height: "130dp"
'''


class MenuScreen(Screen):
    """Halaman Menu Utama"""
    pass


class KalkulatorScreen(Screen):
    """Halaman Kalkulator - logika perhitungan"""

    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.ekspresi = ""
        self.hasil = "0"
        self.sudah_hitung = False

    def tekan_tombol(self, tombol):
        """Fungsi utama yang menangani semua input tombol"""

        layar_ekspresi = self.ids.layar_ekspresi
        layar_hasil = self.ids.layar_hasil

        # ---- TOMBOL CLEAR ----
        if tombol == "C":
            self.ekspresi = ""
            self.hasil = "0"
            self.sudah_hitung = False
            layar_ekspresi.text = "0"
            layar_hasil.text = "0"

        elif tombol == "DEL":
            if self.ekspresi:
                self.ekspresi = self.ekspresi[:-1]
                tampil = self.ekspresi.replace("*", "x").replace("/", "÷")
                layar_ekspresi.text = tampil if tampil else "0"
            self.sudah_hitung = False

        elif tombol == "=":
            if self.ekspresi:
                try:
                    hasil_hitung = eval(self.ekspresi)

                    if isinstance(hasil_hitung, float) and hasil_hitung.is_integer():
                        self.hasil = str(int(hasil_hitung))
                    else:
                        self.hasil = str(round(hasil_hitung, 8))

                    layar_hasil.text = self.hasil
                    self.sudah_hitung = True

                except ZeroDivisionError:
                    layar_hasil.text = "Tidak bisa bagi 0!"
                    self.ekspresi = ""
                    self.sudah_hitung = False

                except Exception:
                    layar_hasil.text = "Error"
                    self.ekspresi = ""
                    self.sudah_hitung = False

        else:
            if self.sudah_hitung and tombol in ["+", "-", "*", "/"]:
                self.ekspresi = self.hasil + tombol
                self.sudah_hitung = False

            elif self.sudah_hitung and tombol not in ["+", "-", "*", "/"]:
                self.ekspresi = tombol
                self.sudah_hitung = False

            else:
                # Cegah dua titik dalam satu angka
                if tombol == ".":
                    import re
                    bagian = re.split(r'[+\-*/]', self.ekspresi)
                    angka_terakhir = bagian[-1] if bagian else ""
                    if "." in angka_terakhir:
                        return

                if tombol in ["+", "-", "*", "/"]:
                    if self.ekspresi and self.ekspresi[-1] in ["+", "-", "*", "/"]:
                        self.ekspresi = self.ekspresi[:-1]

                self.ekspresi += tombol

            tampil = self.ekspresi.replace("*", "x").replace("/", "÷")
            layar_ekspresi.text = tampil
            layar_hasil.text = self.hasil


class TentangScreen(Screen):
    """Halaman Tentang Aplikasi"""
    pass

class CalcSimpleApp(MDApp):

    def build(self):
        self.theme_cls.theme_style = "Dark"
        self.theme_cls.primary_palette = "Orange"
        self.title = "CalcSimple"

        return Builder.load_string(KV)


if __name__ == "__main__":
    CalcSimpleApp().run()
