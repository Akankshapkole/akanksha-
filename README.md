createStudent() {
    this.service.createStudent(this.student)
    .subscribe(data => {
      this.message = data; // read message
      this.student = new Student(); // clear form
    }, error => {
      console.log(error);
    });
  }
