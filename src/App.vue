<template>
  <div>
    <h1 style="text-align: center; margin-top: 50px;">Kirim Email</h1>

    <!-- Formulir untuk mengirim email -->
    <form @submit.prevent="sendEmail" style="margin: 0 auto; max-width: 400px;">
      <!-- Input untuk alamat email penerima -->
      <div class="form-group">
        <label for="recipient" :style="{ color: recipientColor }">Penerima:</label>
        <input type="email" id="recipient" v-model="recipient" class="form-control" :style="{ color: recipientColor }" placeholder="Email penerima" required>
      </div>
    
      <!-- Dropdown untuk memilih warna font penerima -->
      <div class="form-group">
        <label>Pilih Warna Font Penerima:</label>
        <select v-model="recipientColor" style="margin-bottom: 25px;">
          <option value="black">Hitam</option>
          <option value="red">Merah</option>
          <option value="yellow">Kuning</option>
          <option value="brown">Coklat</option>
        </select>
      </div>

      <!-- Input untuk subjek email -->
      <div class="form-group">
        <label for="subject" :style="{ color: subjectColor }">Subjek:</label>
        <input type="text" id="subject" v-model="subject" class="form-control" :style="{ color: subjectColor }" placeholder="Subjek email" required>
      </div>
      
      <!-- Dropdown untuk memilih warna font subjek -->
      <div class="form-group">
        <label>Pilih Warna Font Subjek:</label>
        <select v-model="subjectColor" style="margin-bottom: 25px;">
          <option value="black">Hitam</option>
          <option value="red">Merah</option>
          <option value="blue">Biru</option>
          <option value="brown">Coklat</option>
        </select>
      </div>

      <!-- Input untuk isi pesan email -->
      <div class="form-group">
        <label for="message" :style="{ color: messageColor }">Pesan:</label>
        <textarea id="message" v-model="message" class="form-control" :style="{ color: messageColor }" rows="5" placeholder="Isi pesan email" required></textarea>
      </div>
      
      <!-- Dropdown untuk memilih warna font pesan -->
      <div class="form-group">
        <label>Pilih Warna Font Pesan:</label>
        <select v-model="messageColor" style="margin-bottom: 25px;">
          <option value="black">Hitam</option>
          <option value="red">Merah</option>
          <option value="blue">Biru</option>
          <option value="brown">Coklat</option>
        </select>
      </div>

      <!-- Tombol untuk mengirim email -->
      <button type="submit" class="btn btn-primary" style="width: 100%;">Kirim</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      recipient: '',
      recipientColor: 'black',
      subject: '',
      subjectColor: 'black',
      message: '',
      messageColor: 'black'
    };
  },
  methods: {
    sendEmail() {
      // Kirim email menggunakan data formulir
      const email = {
        recipient: this.recipient,
        subject: this.subject,
        message: this.message
      };

      // Di sini Anda bisa menambahkan logika untuk mengirim email, misalnya menggunakan axios atau fetch
      // Kemudian Anda bisa melakukan sesuatu setelah email terkirim, seperti menampilkan pesan sukses
      console.log('Email telah terkirim:', email);

      // Reset formulir setelah email terkirim
      this.recipient = '';
      this.subject = '';
      this.message = '';

      // Tampilkan pesan sukses
      alert('Email berhasil terkirim!');
    }
  }
};
</script>

<style scoped>
.form-group {
  margin-bottom: 20px;
}
</style>