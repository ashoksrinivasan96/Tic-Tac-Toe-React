# Tic-Tac-Toe-React

One of the first few React website projects I will be taking on.
This project is a take on restaurant websites and my version of a perfect portfolio for them.

## Motivation
I started out with a very basic idea of making a website for a restaurant owner. The progress was spread through weeks and turned out to be pretty challenging.
It taught me several concepts as well as perseverance to actually close a project properly 😀

## Screenshots

### Mobile screen
<img src="assets/mobile.png" width="170px" height="300px">

### Tab screen
<img src="assets/tab.png" width="240px" height="300px">

### Web screen
<img src="assets/web.png" width="300px" height="300px">


## Tech/Frameworks Used
React, Redux, JSX, HTML, CSS, Javascript, JSON

## Features
* Fully responsive website (web, tablet and mobile)
* Clean minimal design
* Dark Theme
* Customisable template for any needs
* Executes the requirements of a restaurant

## Code Example
Function to Render dish and comments on the Menu page

    function RenderDishAndComments({dish, comments,dishId, postComment}) {
       //Checking if the value of the parameter passed is null or not. If null, return empty view
        if (dish != null && comments != null) {
            const displayComments =comments.map((cmt) => {
                return (
                    <ListGroup key={cmt.id}>
                        {/* Converting date to the required format using toDateString()*/}
                        <ListGroupItem>{cmt.comment}<br></br> --{cmt.author}, {new Intl.DateTimeFormat('en-US', {year:'numeric', month: 'short', day: '2-digit'}).format(new Date(Date.parse(cmt.date)))}</ListGroupItem>

                    </ListGroup>
                );
            });
            return (
               
                <div className="row">
                     {/*returning view with the selected image and the corresponding comments*/}
                    <div className="col-12 col-md-5 col-xl-5 col-lg-5 m-1">
                       <FadeTransform
                in
                transformProps={{
                    exitTransform: 'scale(0.5) translateY(-50%)'
                }}>
            <Card>
                <CardImg top src={baseUrl + dish.image} alt={dish.name} />
                <CardBody>
                    <CardTitle>{dish.name}</CardTitle>
                    <CardText>{dish.description}</CardText>
                </CardBody>
            </Card>
            </FadeTransform>
                    </div>
                    <div className="col-12 col-md-5 col-xl-5 col-lg-5 m-1">
                        <h4>Comments</h4>
                       <Stagger in>
                           <Fade>
                              {displayComments}
                           </Fade>
                       </Stagger>
                      
                       
                        <CommentForm dishId={dishId} postComment={postComment} />
                    </div>
                </div>

            );

        }
        else {
            return (
                <div></div>
            );
        }
    }

## Link to the website
Find the website [here](https://exoticdelikabi.herokuapp.com/home)

## Credits
**©Ashok Srinivasan| 2020**
