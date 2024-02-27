<template>
    <div  class="relative bg-gradient-to-tl from-[#6a51aa] to-[#A194C5] min-h-screen">
        <Navbar></Navbar>
        <div>
            <slot></slot>
        </div>
        <FaqButton class="fixed bottom-5 right-5"></FaqButton>
    </div>
</template>