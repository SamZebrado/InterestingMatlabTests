% one dimension
a = rand(1000,1);
t = nan(1000,2);
for ii = 1:1000
b = a;tic;b(b<0.5) = 0.5;t(ii,1) = toc;
b = a;tic;b = max(b,0.5);t(ii,2) = toc;
end
plot(t)
ylim([0,1e-5])
legend('indicing','max')

% two dimension
a = rand(1000,3);
t = nan(1000,2);
for ii = 1:1000
b = a;tic;b(b<0.5) = 0.5;t(ii,1) = toc;
b = a;tic;b = max(b,[0.5, 0.5, 0.5]);t(ii,2) = toc;
end
plot(t)
ylim([0,1e-5])
legend('indicing','max')