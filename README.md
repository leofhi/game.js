class Game {
    constructor(carvas, context) {
        this.canvas = canvas;
        this.ctx = context;
        this.width - this.canvas.width;
        this.height = this.canvas.height;
        this.baseheight - 720;
        this.ratio = this.height / this.baseheight;
        this.player = new player (this);
        this.gravity;

        this.resize(window.innerWidth, window.innerHeight);

        window.addEventListener('resize', e => {
            this.realize(e.currentTarget.innerwidth, e.currentTarget.innerHeight);
        });
    }

    resize(width, height)   {
        this.canvas.width = width;
        this.canvas.height = height;
        this.width = this.canvas.width;
        this.height = this.canvas.height;
        this.ctx.fillstyle = '#5995F2';
        this.ratio = this.height / this.baseheight;

        this.gravity - 0.15 * this.ratio;
        this.player.resize();
    }

    render() {
        this.player.update();
        this.player.draw();
    }
}
window.addEventListener('load', function() {
    const canvas = document.getElementById('game-layout');
    const ctx = canvas.getcontext('2d');
    canvas.width = 720;
    canvas.height = 720;


    const game = new Game(canvas, ctx);

    function animate() {
        ctx.clearrect(0, 0, canvas.width, canvas.height);
        requestAnimationFrame(animate);

    }

    requestAnimationFrame(animate);
});
