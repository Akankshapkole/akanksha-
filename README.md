ngOnInit(): void {
    // read id sent by all component as /edit/id
    // tslint:disable-next-line: no-string-literal
    this.id = this.activatedRoute.snapshot.params['id'];
    // make service call to get student object
    this.service.getOneStudent(this.id).subscribe(
      data => {
      this.student = data;
      console.log(this.student);
    }, error => {
      console.log(error);
    });
  }

  // tslint:disable-next-line: typedef
  updateStudent() {
    this.service.updateStudent(this.id, this.student)
    .subscribe( data => {
      console.log(data);
      this.router.navigate(['all']);
    });
  }
